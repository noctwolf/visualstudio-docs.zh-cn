---
title: 创建并运行托管代码的单元测试
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- unit tests, walkthrough
- unit tests, creating
- unit tests, generating
- unit tests, running
- unit tests, authoring
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
author: gewarren
ms.openlocfilehash: 537059a78ccc316b7b74a8300961b57b4e6e6f95
ms.sourcegitcommit: 38db86369af19e174b0aba59ba1918a5c4fe4a61
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2019
ms.locfileid: "54269977"
---
# <a name="walkthrough-create-and-run-unit-tests-for-managed-code"></a>演练：创建并运行托管代码的单元测试

本文将使用托管代码的 Microsoft 单元测试框架和 Visual Studio 测试资源管理器引导你逐步完成一系列单元测试的创建、运行和自定义。 你将从正处于开发过程中的 C# 项目开始，创建执行该项目代码的测试，运行测试并检查结果。 然后，可以更改项目代码并重新运行测试。

> [!NOTE]
> 此演练使用用于托管代码的 Microsoft 单元测试框架。 “测试资源管理器”还可以在具有“测试资源管理器”适配器的第三方单元测试框架中运行测试。 有关详细信息，请参阅[安装第三方单元测试框架](../test/install-third-party-unit-test-frameworks.md)

有关如何从命令行运行测试的信息，请参阅 [VSTest.Console.exe 命令行选项](vstest-console-options.md)。

## <a name="prerequisites"></a>系统必备

- Bank 项目。 请参阅[用于创建单元测试的示例项目](../test/sample-project-for-creating-unit-tests.md)。

## <a name="create-a-project-to-test"></a>创建一个项目进行测试

1. 打开 Visual Studio。

2. 在“文件”菜单上，选择“新建” > “项目”。

   此时将出现 “新建项目” 对话框。

3. 在 **“已安装的模板”** 下单击 **“Visual C#”**。

4. 在应用程序类型的列表中单击 **“类库”**。

5. 在“名称”框中键入 Bank，然后单击“确定”。

   将创建新的 Bank 项目并将其显示在“解决方案资源管理器”中，而且将在代码编辑器中打开 Class1.cs 文件。

   > [!NOTE]
   > 如果代码编辑器中未打开 Class1.cs，请在“解决方案资源管理器”中双击文件 Class1.cs 将其打开。

6. 从[用于创建单元测试的示例项目](../test/sample-project-for-creating-unit-tests.md)中复制源代码，并将 Class1.cs 的原始内容替换为复制的代码。

7. 将文件保存为 BankAccount.cs。

8. 在 **“生成”** 菜单上，单击 **“生成解决方案”**。

现在你有一个名为“Bank”的项目。 它包含要测试的源代码和用于对该源代码进行测试的工具。 Bank 的命名空间“BankAccountNS”包含公共类“BankAccount”，在以下过程中将对该类的方法进行测试。

在本文中，测试侧重于 Debit 方法。 在从帐户提取资金时调用 Debit 方法。 下面是该方法定义：

```csharp
// Method to be tested.
public void Debit(double amount)
{
    if(amount > m_balance)
    {
        throw new ArgumentOutOfRangeException("amount");
    }
    if (amount < 0)
    {
        throw new ArgumentOutOfRangeException("amount");
    }
    m_balance += amount;
}
```

## <a name="create-a-unit-test-project"></a>创建单元测试项目

1. 在“文件”菜单上，选择“添加” > “新建项目”。

2. 在“新建项目”对话框中，依次展开“已安装”、“Visual C#”，然后选择“测试”。

3. 从模板列表中选择 **“单元测试项目”**。

4. 在“名称”框中，输入 `BankTests`，然后选择“确定”。

   将“BankTests”项目添加到“Bank”解决方案。

5. 在“BankTests”项目中，添加对“Bank”项目的引用。

   在“解决方案资源管理器”中，依次选择“BankTests”项目中的“引用”，以及右键单击菜单中的“添加引用”。

6. 在“引用管理器”对话框中，展开“解决方案”，然后选中“Bank”项。

## <a name="create-the-test-class"></a>创建测试类

创建一个测试类来验证 `BankAccount` 类。 可以使用项目模板生成的 UnitTest1.cs 文件，但需为文件和类提供更具描述性的名称。 通过重命名“解决方案资源管理器”中的文件，一步即可完成该操作。

### <a name="rename-a-class-file"></a>重命名类文件

在“解决方案资源管理器”中，从 BankTests 项目中选择 UnitTest1.cs 文件。 在右键单击菜单中，选择“重命名”，再将文件重命名为 BankAccountTests.cs。 在询问是否希望重命名项目中对码位元素 `UnitTest1` 的所有引用的对话框中，选择“是”。

此步骤会将类的名称更改为 `BankAccountTests`。 BankAccountTests.cs 文件现包含下列代码：

```csharp
using System;
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace BankTests
{
    [TestClass]
    public class BankAccountTests
    {
        [TestMethod]
        public void TestMethod1()
        {
        }
    }
}
```

### <a name="add-a-using-statement-to-the-project-under-test"></a>向所测试项目添加 using 语句

还可以向类中添加 `using` 语句以供项目调用，而无需使用完全限定名。 在类文件顶部添加：

```csharp
using BankAccountNS;
```

### <a name="test-class-requirements"></a>测试类要求

对测试类的最低要求有：

- 在托管代码的 Microsoft 单元测试框架中，任何包含要在“测试资源管理器”中运行的单元测试方法的类都需要有 `[TestClass]` 特性。

- 你希望“测试资源管理器”运行的每个测试方法都必须具有 `[TestMethod]` 属性。

单元测试项目中可以具有不含 `[TestClass]` 特性的其他类，测试类中可以具有不含 `[TestMethod]` 特性的其他方法。 可以在测试方法中使用这些其他的类和方法。

## <a name="create-the-first-test-method"></a>创建第一个测试方法

在此过程中，编写单元测试方法以验证 `BankAccount` 类的 `Debit` 方法的行为。 `Debit` 方法之前已在本文中显示。

至少需要检查三种行为：

- 如果借方金额大于余额，该方法将引发 <xref:System.ArgumentOutOfRangeException> 。

- 如果借方金额小于零，该方法会引发 <xref:System.ArgumentOutOfRangeException>。

- 如果借方金额有效，该方法会从帐户余额中减去该借方金额。

> [!TIP]
> 可以删除默认的 `TestMethod1` 方法，因为本演练中不会用到它。

### <a name="to-create-a-test-method"></a>创建测试方法

第一个测试验证是否从帐户中提取了正确的有效金额（即小于帐户余额且大于零）。 将以下方法添加到该 `BankAccountTests` 类：

```csharp
[TestMethod]
public void Debit_WithValidAmount_UpdatesBalance()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 4.55;
    double expected = 7.44;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    account.Debit(debitAmount);

    // Assert
    double actual = account.Balance;
    Assert.AreEqual(expected, actual, 0.001, "Account not debited correctly");
}
```

该方法非常简单：它设置了具有期初余额的新 `BankAccount` 对象，然后提取有效金额。 它使用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A> 方法验证期末余额是否和预期一样。

### <a name="test-method-requirements"></a>测试方法要求

测试方法必须满足以下要求：

- 使用 `[TestMethod]` 特性进行修饰。

- 它将返回 `void`。

- 它不能含有参数。

## <a name="build-and-run-the-test"></a>生成并运行测试

1. 在 **“生成”** 菜单上，选择 **“生成解决方案”**。

   如果没有错误，会显示“测试资源管理器”，其中 Debit_WithValidAmount_UpdatesBalance 在“未运行的测试”组中列出。

   > [!TIP]
   > 如果“测试资源管理器”在成功生成后未显示，请在菜单上选择 “测试”，再选择“窗口”，然后选择“测试资源管理器”。

2. 选择 **“全部运行”** 以运行测试。 测试运行时，窗口顶部的状态栏呈动态。 测试运行结束时，如果测试方法全部通过，状态栏将变为绿色；如果有任何测试失败，状态栏将变为红色。

3. 在这种情况下，测试失败。 测试方法将移动到“失败的测试”组。 在“测试资源管理器”中选择该方法，可在窗口底部查看详细信息。

## <a name="fix-your-code-and-rerun-your-tests"></a>修复代码并重新运行测试

### <a name="analyze-the-test-results"></a>分析测试结果

测试结果包含一条描述失败的消息。 对于 `AreEqual` 方法，消息会显示预期的内容（Expected\<value> 参数）以及实际接收到的内容（Actual\<value> 参数）。 虽然预计余额会减少，但余额中反而增加了取款金额。

单元测试已发现一个 bug：取款金额本应从帐户余额中减去，结果却添加到帐户余额中。

### <a name="correct-the-bug"></a>更正 bug

若要更正错误，请将代码行：

```csharp
m_balance += amount;
```

替换为：

```csharp
m_balance -= amount;
```

### <a name="rerun-the-test"></a>重新运行测试

在测试资源管理器中，选择“全部运行”以重新运行测试。 红色/绿色栏会变为绿色（表示测试通过），且测试将移动到“已通过的测试”组。

## <a name="use-unit-tests-to-improve-your-code"></a>使用单元测试以改进代码

本部分介绍了分析的迭代过程、单元测试开发和重构如何帮助你增加成品代码的可靠性和有效性。

### <a name="analyze-the-issues"></a>分析问题

已创建测试方法，以确认是否在 `Debit` 方法中正确扣除了有效金额。 现在，验证若借方金额为以下情况，该方法是否会引发 <xref:System.ArgumentOutOfRangeException>：

- 大于余额，或
- 小于零。

### <a name="create-the-test-methods"></a>创建测试方法

创建测试方法，验证借方金额小于零时的行为是否正确：

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentOutOfRangeException))]
public void Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = -100.00;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    account.Debit(debitAmount);

    // Assert is handled by the ExpectedException attribute on the test method.
}
```

使用 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> 特性断言已引发正确的异常。 除非 <xref:System.ArgumentOutOfRangeException> 已抛出，否则该特性将导致测试失败。 如果在借方金额小于零时临时修改测试方法以引发更通用的 <xref:System.ApplicationException>，则测试将正确运行 &mdash; 即测试将失败。

若要测试提取金额大于余额的情况，执行以下操作：

1. 新建一个名为 `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange`的测试方法。

2. 将 `Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange` 中的方法主体复制到新方法中。

3. 将 `debitAmount` 设置为比余额大的一个数字。

### <a name="run-the-tests"></a>运行测试

运行这两个测试方法证明了测试工作正常。

### <a name="continue-the-analysis"></a>继续分析

但是，最后两个测试方法也很麻烦。 在任一测试运行时，无法确定测试方法在哪些情况下会引发异常。 用于区分这两种情况（即负借方金额或大于余额的金额）的某种方式将增加你对测试的信心。

让我们再看看测试方法，请注意两个条件语句都使用 `ArgumentOutOfRangeException` 构造函数，该函数将自变量名称作为参数：

```csharp
throw new ArgumentOutOfRangeException("amount");
```

可以使用报告的信息更加丰富的构造函数：<xref:System.ArgumentOutOfRangeException.%23ctor(System.String,System.Object,System.String)> 包括自变量的名称、自变量的值和用户定义消息。 可以重构被测方法以使用此构造函数。 更理想的做法是使用公开的类型成员来指定错误。

### <a name="refactor-the-code-under-test"></a>重构所测试的代码

首先，为类范围内的错误消息定义两个常量。 将这些常量置于测试类中，BankAccount：

```csharp
public const string DebitAmountExceedsBalanceMessage = "Debit amount exceeds balance";
public const string DebitAmountLessThanZeroMessage = "Debit amount is less than zero";
```

然后，修改 `Debit` 方法中的两个条件语句：

```csharp
    if (amount > m_balance)
    {
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountExceedsBalanceMessage);
    }

    if (amount < 0)
    {
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountLessThanZeroMessage);
    }
```

### <a name="refactor-the-test-methods"></a>重构测试方法

删除 `ExpectedException` 测试方法特性，改为捕获引发的异常并验证其关联的消息。 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Contains%2A?displayProperty=fullName> 方法提供比较两个字符串的功能。

现在，`Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` 可能如下所示：

```csharp
[TestMethod]
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 20.0;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    try
    {
        account.Debit(debitAmount);
    }
    catch (ArgumentOutOfRangeException e)
    {
        // Assert
        StringAssert.Contains(e.Message, BankAccount.DebitAmountExceedsBalanceMessage);
    }
}
```

### <a name="retest-rewrite-and-reanalyze"></a>重测、重写和重新分析

假定测试方法中存在一个 bug 且 `Debit` 方法没有引发 <xref:System.ArgumentOutOfRangeException>，也没有输出有关该异常的正确消息。 目前，测试方法无法处理这种情况。 如果 `debitAmount` 值有效（即小于余额，但大于零），则不会捕获到异常，因此永远不会触发该断言。 但是测试方法通过了。 这样并不好，因为如果未引发异常，则希望测试方法失败。

这是测试方法中的一个 bug。 要解决该问题，在测试方法末尾添加 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> 断言，处理未引发异常的情况。

但重新运行测试表明，如果捕获到正确的异常，测试现将失败。 `catch` 块捕获到该异常，但该方法继续执行，并在新的 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> 断言处失败。 要解决此问题，在 `catch` 块中的 `StringAssert` 后添加 `return` 语句。 重新运行测试可确认已解决此问题。 `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` 的最终版本如下：

```csharp
[TestMethod]
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 20.0;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    try
    {
        account.Debit(debitAmount);
    }
    catch (ArgumentOutOfRangeException e)
    {
        // Assert
        StringAssert.Contains(e.Message, BankAccount.DebitAmountExceedsBalanceMessage);
        return;
    }

    Assert.Fail("The expected exception was not thrown.");
}
```

通过改进测试代码，可使测试方法更可靠并提供更多信息。 但更重要的是，被测代码也得到改进。
