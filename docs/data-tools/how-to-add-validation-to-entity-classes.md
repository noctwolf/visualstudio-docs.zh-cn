---
title: 如何：在实体类中添加验证
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 61107da9-7fa3-4dba-b101-ae46536f52c4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: b91fc7fb356ebd0db4a0bd7960ac060e7d152ec1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63402844"
---
# <a name="how-to-add-validation-to-entity-classes"></a>如何：在实体类中添加验证
验证实体类是指确认输入到数据对象中的值是否符合对象架构内的约束，以及是否符合为应用程序所建立的规则的过程。 在将更新发送到基础数据库之前对数据进行验证是一种很好的做法，这样可以减少错误。 还可以减少应用程序和数据库之间的潜在往返行程次数。

 [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)提供了使用户可以扩展运行期间的插入、 更新和删除完整实体，并还期间和之后各列的设计器生成代码的分部方法更改。

> [!NOTE]
> 本主题将验证添加到实体类，通过使用提供的基本步骤**O/R 设计器**。 它可能很难参考特定实体类的情况下执行这些通用步骤，因为提供的演练，使用实际数据。

## <a name="add-validation-for-changes-to-the-value-in-a-specific-column"></a>将更改的验证添加到特定列中的值
 此过程演示当列中的值更改时如何验证数据。 由于验证在类定义（而不是用户界面）中执行，因此如果值导致验证失败，则将引发异常。 请为应用程序中试图更改列值的代码实现错误处理。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-validate-data-during-a-columns-value-change"></a>在列值更改过程中验证数据

1. 打开或创建一个新的 LINQ to SQL 类文件 (**.dbml**文件) 中**O/R 设计器**。 （在“解决方案资源管理器”中双击“.dbml”文件。）

2. 在 O/R 设计器中，右键单击要为其添加验证的类，然后单击“查看代码”。

     将打开代码编辑器，其中显示所选实体类的分部类。

3. 将光标放在该分部类中。

4. 对于 Visual Basic 项目：

    1. 展开“方法名称”列表。

    2. 定位到要为其添加验证的列的 OnCOLUMNNAMEChanging 方法。

    3. `OnCOLUMNNAMEChanging` 方法将添加到分部类中。

    4. 添加下列代码，以首先确认是否已输入了值，然后确保为该列输入的值可被你的应用程序接受。 `value` 自变量包含建议的值，因此添加逻辑以确认它是否为有效值：

        ```vb
        If value.HasValue Then
            ' Add code to ensure that the value is acceptable.
            ' If value < 1 Then
            '    Throw New Exception("Invalid data!")
            ' End If
        End If
        ```

    对于 C# 项目：

    由于 C# 项目不会自动生成事件处理程序，您可以使用 IntelliSense 创建列更改分部方法。 键入 `partial` 和空格以访问可用分部方法的列表。 单击要为其添加验证的列的列更改方法。 下面的代码类似于您选择的列更改分部方法时生成的代码：

    ```csharp
    partial void OnCOLUMNNAMEChanging(COLUMNDATATYPE value)
        {
           throw new System.NotImplementedException();
        }
    ```

## <a name="add-validation-for-updates-to-an-entity-class"></a>向实体类中添加更新的验证
 除了可以在更改过程中检查值之外，还可以在尝试更新完整实体类时验证数据。 在尝试进行更新操作的过程中进行的验证可以比较多个列中的值（如果业务规则要求这样做）。 下面的过程演示在尝试更新完整实体类时如何进行验证。

> [!NOTE]
> 更新完整实体类的验证代码是在分部 <xref:System.Data.Linq.DataContext> 类（而不是在特定实体类的分部类）中执行的。

### <a name="to-validate-data-during-an-update-to-an-entity-class"></a>在实体类更新过程中验证数据

1. 打开或创建一个新的 LINQ to SQL 类文件 (**.dbml**文件) 中**O/R 设计器**。 （在“解决方案资源管理器”中双击“.dbml”文件。）

2. 右键单击 O/R 设计器上的空白区域，然后单击“查看代码”。

     将打开代码编辑器，其中显示 `DataContext` 的一个分部类。

3. 将光标放在 `DataContext` 的分部类上。

4. 对于 Visual Basic 项目：

    1. 展开“方法名称”列表。

    2. 单击“UpdateENTITYCLASSNAME”。

    3. `UpdateENTITYCLASSNAME` 方法将添加到分部类中。

    4. 使用 `instance` 参数访问各个列值，如下面的代码所示：

        ```vb
        If (instance.COLUMNNAME = x) And (instance.COLUMNNAME = y) Then
            Dim ErrorMessage As String = "Invalid data!"
            Throw New Exception(ErrorMessage)
        End If
        ```

    对于 C# 项目：

    由于 C# 项目不会自动生成事件处理程序，您可以使用 IntelliSense 创建分部`UpdateCLASSNAME`方法。 键入 `partial` 和空格以访问可用分部方法的列表。 单击你想要添加验证的类的更新方法。 下面的代码类似于您选择时生成的代码`UpdateCLASSNAME`分部方法：

    ```csharp
    partial void UpdateCLASSNAME(CLASSNAME instance)
    {
        if ((instance.COLUMNNAME == x) && (instance.COLUMNNAME = y))
        {
            string ErrorMessage = "Invalid data!";
            throw new System.Exception(ErrorMessage);
        }
    }
    ```

## <a name="see-also"></a>请参阅

- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [验证数据](../data-tools/validate-data-in-datasets.md)
- [LINQ to SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)