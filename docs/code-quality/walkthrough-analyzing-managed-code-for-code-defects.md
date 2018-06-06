---
title: 演练对托管代码进行代码缺陷 |Microsoft 文档
ms.date: 01/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis [Visual Studio]
- managed code, analyzing
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: a353d7a61f9bc1dbb83d37ad419c3d2fbdf656ba
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746554"
---
# <a name="walkthrough-analyzing-managed-code-for-code-defects"></a>演练： 代码的分析托管的代码缺陷

在本演练中，你将通过使用代码分析工具来分析托管的项目进行代码缺陷。

本演练将引导你完成使用代码分析来分析你的.NET 托管代码程序集，为了符合 Microsoft.NET Framework 设计准则的过程。

## <a name="create-a-class-library"></a>创建一个类库

### <a name="to-create-a-class-library"></a>若要创建一个类库

1. 在“文件”菜单上，选择“新建” > “项目...”。

1. 在**新项目**对话框框中，展开**已安装** > **Visual C#**，然后选择**Windows 桌面**。

1. 选择**类库 (.NET Framework)** 模板。

1. 在**名称**文本框中，键入**CodeAnalysisManagedDemo** ，然后单击**确定**。

1. 创建项目后，打开*Class1.cs*文件。

1. 用下面的代码替换 Class1.cs 中的现有文本：

   ```csharp
   using System;

   namespace testCode
   {
       public class demo : Exception
       {
           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int item { get { return _item; } }
       }
   }
   ```

1. 保存 Class1.cs 文件。

## <a name="analyze-the-project"></a>分析项目

### <a name="to-analyze-a-managed-project-for-code-defects"></a>若要分析托管的项目进行代码缺陷

1. 选择中的 CodeAnalysisManagedDemo 项目**解决方案资源管理器**。

1. 在“项目”菜单上，单击“属性”。

     将显示 CodeAnalysisManagedDemo 属性页。

1. 选择**代码分析**选项卡。

1. 请确保**生成时启用代码分析**已选中。

1. 从**运行此规则集**下拉列表中，选择**Microsoft 所有规则**。

1. 上**文件**菜单上，单击**保存选定项**，然后关闭属性页。

1. 上**生成**菜单上，单击**生成 CodeAnalysisManagedDemo**。

    CodeAnalysisManagedDemo 项目生成警告形式均为**错误列表**和**输出**windows。

## <a name="correct-the-code-analysis-issues"></a>更正代码分析问题

### <a name="to-correct-code-analysis-rule-violations"></a>若要更正代码分析规则冲突

1. 上**视图**菜单上，选择**错误列表**。

    根据你选择的开发人员配置文件，你可能必须指向**其他窗口**上**视图**菜单，然后选择**错误列表**。

1. 在**解决方案资源管理器**，选择**显示所有文件**。

1. 展开属性节点，然后打开*AssemblyInfo.cs*文件。

1. 使用以下提示以更正警告：

   [CA1014： 将程序集用 CLSCompliantAttribute 标记](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md): Microsoft.Design： 用 CLSCompliantAttribute，应标记为 demo，其值应为 true。

   1. 将代码添加`using System;`AssemblyInfo.cs 文件。

   1. 接下来，将代码添加`[assembly: CLSCompliant(true)]`到 AssemblyInfo.cs 文件末尾。

   [CA1032： 实现标准异常构造函数](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design： 与此类添加下面的构造函数： 公共 demo(String)

   1. 添加的构造函数`public demo (String s) : base(s) { }`到类`demo`。

   [CA1032： 实现标准异常构造函数](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design： 与此类添加下面的构造函数： 公共演示 （String，异常）

   1. 添加的构造函数`public demo (String s, Exception e) : base(s, e) { }`到类`demo`。

   [CA1032： 实现标准异常构造函数](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design： 与此类添加下面的构造函数： 保护演示 （SerializationInfo，StreamingContext）

   1. 将代码添加`using System.Runtime.Serialization;`到 Class1.cs 文件的开头。

   1. 接下来，添加构造函数 `protected demo (SerializationInfo info, StreamingContext context) : base(info, context) { } to the class demo.`

   [CA1032： 实现标准异常构造函数](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design： 与此类添加下面的构造函数： 公共 demo()

   1. 添加的构造函数`public demo () : base() { }`到类`demo` **。**

   [CA1709： 标识符应采用正确的大小写](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming： 通过将其更改为 TestCode 更正的命名空间名称 testCode 大小写。

   1. 更改命名空间的大小写`testCode`到`TestCode`。

   [CA1709： 标识符应采用正确的大小写](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming： 更正其更改为 Demo 的类型名称 demo 的大小写。

   1. 更改的成员名称`Demo`。

   [CA1709： 标识符应采用正确的大小写](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming： 更正其更改为 Item 的成员名称 item 的大小写。

   1. 更改的成员名称`Item`。

   [CA1710： 标识符应具有正确的后缀](../code-quality/ca1710-identifiers-should-have-correct-suffix.md): Microsoft.Naming： 重命名 testCode.demo 以 Exception 结尾。

   1. 更改的类并向其构造函数的名称`DemoException`。

   [CA2210： 程序集应具有有效的强名称](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md)： 使用强名称密钥进行签名 CodeAnalysisManagedDemo。

   1. 上**项目**菜单上，选择**CodeAnalysisManagedDemo 属性**。

      显示项目属性。

   1. 选择 **“签名”** 选项卡。

   1. 选择**对程序集签名**复选框。

   1. 在**选择字符串名称密钥文件**列表中，选择**\<新建 … >**。

      **创建强名称密钥**对话框随即出现。

   1. 在**密钥文件名称**，键入为 TestKey。

   1. 输入密码，然后选择**确定**。

   1. 上**文件**菜单上，选择**保存选定项**，然后关闭属性页。

   [CA2237： 以 SerializableAttribute 标记 ISerializable 类型](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md): Microsoft.Usage： 添加要键入 demo 是此类型实现 ISerializable 的 [Serializable] 属性。

   1. 添加`[Serializable ()]`到类属性`demo`。

   在完成更改后，Class1.cs 文件应如下所示：

   ```csharp
   using System;
   using System.Runtime.Serialization;

   namespace TestCode
   {
       [Serializable()]
       public class DemoException : Exception
       {
           public DemoException () : base() { }
           public DemoException(String s) : base(s) { }
           public DemoException(String s, Exception e) : base(s, e) { }
           protected DemoException(SerializationInfo info, StreamingContext context) : base(info, context) { }

           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int Item { get { return _item; } }
       }
   }
   ```

1. 重新生成项目。

## <a name="exclude-code-analysis-warnings"></a>排除代码分析警告

### <a name="to-exclude-code-defect-warnings"></a>若要排除代码缺陷警告

1. 对于每一个剩余警告，请执行以下操作：

    1. 选择在警告**错误列表**。

    1. 从右键单击或上下文菜单中选择**禁止** > **在禁止显示文件**。

1. 重新生成项目。

     生成项目，并且没有任何警告或错误。

## <a name="see-also"></a>请参阅

[针对托管代码的代码分析](../code-quality/code-analysis-for-managed-code-overview.md)