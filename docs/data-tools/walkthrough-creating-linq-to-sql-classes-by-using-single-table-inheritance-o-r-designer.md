---
title: 演练： 创建 LINQ to SQL 类通过使用单表继承 （O-R 设计器）
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 63bc6328-e0df-4655-9ce3-5ff74dbf69a4
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 943b75c9c5f9c0c32ab02b5e73c07282728e0beb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49864720"
---
# <a name="walkthrough-create-linq-to-sql-classes-by-using-single-table-inheritance-or-designer"></a>演练： 创建 LINQ to SQL 类通过使用单表继承 （O/R 设计器）
[Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)支持单表继承中，通常是在关系数据库管理系统中实现。 本演练中提供的通用步骤进行了扩展[如何： 通过使用 O/R 设计器配置继承](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)主题，并提供一些真实数据演示了如何使用中的继承[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]。

 在本演练中，你将执行以下任务：

- 创建一个数据库表，并向其中添加数据。

- 创建一个 Windows 窗体应用程序。

- 将一个 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 文件添加到项目。

- 创建新的实体类。

- 配置实体类使用继承。

- 查询继承类。

- 在 Windows 窗体上显示数据。

## <a name="create-a-table-to-inherit-from"></a>创建一个表继承
 若要查看继承的工作方式，创建一个较小`Person`表，将其用作基类，并创建`Employee`从其继承的对象。

### <a name="to-create-a-base-table-to-demonstrate-inheritance"></a>创建基表以演示继承

1.  在中**服务器资源管理器**或**数据库资源管理器**，右键单击**表**节点，然后单击**添加新表**。

    > [!NOTE]
    >  可以使用 Northwind 数据库或其他任何可添加表的数据库。

2.  在中**表设计器**，向表中添加以下列：

    |列名|数据类型|允许为 Null|
    |-----------------|---------------|-----------------|
    |**ID**|**int**|**False**|
    |**Type**|**int**|**True**|
    |**FirstName**|**nvarchar(200)**|**False**|
    |**姓氏**|**nvarchar(200)**|**False**|
    |**管理器**|**int**|**True**|

3.  将 ID 列设置为主键。

4.  保存表并将其命名**人员**。

## <a name="add-data-to-the-table"></a>将数据添加到表
 为了验证对继承的配置是否正确，表对于单表继承中的每个类都需要一些数据。

### <a name="to-add-data-to-the-table"></a>向表中添加数据。

1.  在数据视图中打开该表。 (右键单击**Person**表中**服务器资源管理器**或**数据库资源管理器**然后单击**显示表数据**。)

2.  将下面的数据复制到表中。 (您可以将其复制，然后，通过选择整个行中的，将其粘贴到表**结果**窗格。)

    ||||||
    |-|-|-|-|-|
    |**ID**|**Type**|**FirstName**|**姓氏**|**管理器**|
    |**1**|**1**|**Anne**|**Wallace**|**NULL**|
    |**2**|**1**|**Carlos**|**Grilo**|**NULL**|
    |**3**|**1**|**Yael**|**Peled**|**NULL**|
    |**4**|**2**|**Gatis**|**Ozolins**|**1**|
    |**5**|**2**|**Andreas**|**Hauser**|**1**|
    |**6**|**2**|**Tiffany**|**Phuvasate**|**1**|
    |**7**|**2**|**Alexey**|**Orekhov**|**2**|
    |**8**|**2**|**Michał**|**Poliszkiewicz**|**2**|
    |**9**|**2**|**Tai**|**Yee**|**2**|
    |**10**|**2**|**Fabricio**|**Noriega**|**3**|
    |**11**|**2**|**我**|**Martin**|**3**|
    |**12**|**2**|**Ken**|**Kwok**|**3**|

## <a name="create-a-new-project"></a>创建新项目
 至此，表已经创建完毕，下面创建一个新项目演示对继承的配置。

### <a name="to-create-the-new-windows-forms-application"></a>若要创建新的 Windows 窗体应用程序

1. 在 Visual Studio 中，在**文件**菜单中，选择**新建** > **项目**。

2. 展开**Visual C#** 或**Visual Basic**在左侧窗格中，然后选择**Windows 桌面**。

3. 在中间窗格中，选择**Windows 窗体应用**项目类型。

4. 将项目命名**InheritanceWalkthrough**，然后选择**确定**。

     **InheritanceWalkthrough**项目时创建，并添加到**解决方案资源管理器**。

## <a name="add-a-linq-to-sql-classes-file-to-the-project"></a>LINQ to SQL 类文件，向项目添加

### <a name="to-add-a-linq-to-sql-file-to-the-project"></a>若要添加 LINQ to SQL 文件到项目

1.  在 **“项目”** 菜单上，单击 **“添加新项”**。

2.  单击**LINQ to SQL 类**模板，然后单击**添加**。

     *.Dbml*文件添加到项目并**O/R 设计器**随即打开。

## <a name="create-the-inheritance-by-using-the-or-designer"></a>通过使用 O/R 设计器创建继承
 通过拖动来配置继承**继承**对象从**工具箱**拖到设计图面。

### <a name="to-create-the-inheritance"></a>创建继承

1.  在中**服务器资源管理器**或**数据库资源管理器**，导航到**人员**前面创建的表。

2.  拖动**Person**表拖动到**O/R 设计器**设计图面。

3.  将另一个**Person**表拖动到**O/R 设计器**和其名称更改为**员工**。

4.  删除**管理器**属性从**人员**对象。

5.  删除**类型**， **ID**， **FirstName**，以及**LastName**属性从**员工**对象。 (即，删除所有属性除外**Manager**。)

6.  从**对象关系设计器**选项卡**工具箱**，创建**继承**之间**人员**和**员工**对象。 若要执行此操作，请单击**继承**中的项**工具箱**释放鼠标按钮。 接下来，单击**员工**对象，然后**人员**对象中**O/R 设计器**。 继承连线上的箭头然后指向**人员**对象。

7.  单击**继承**设计图面上的行。

8.  设置**鉴别器属性**属性设置为**类型**。

9. 设置**派生类鉴别器值**属性设置为**2**。

10. 设置**基类鉴别器值**属性设置为**1**。

11. 设置**继承默认值**属性设置为**人员**。

12. 生成项目。

## <a name="query-the-inherited-class-and-display-the-data-on-the-form"></a>查询继承的类并在窗体上显示的数据
 现在查询的对象模型中的特定类的窗体中添加一些代码。

### <a name="to-create-a-linq-query-and-display-the-results-on-the-form"></a>创建一个 LINQ 查询并在窗体上显示结果

1.  拖动**ListBox**拖动到**Form1**。

2.  双击窗体以创建 `Form1_Load` 事件处理程序。

3.  将以下代码添加到 `Form1_Load` 事件处理程序中：

    ```vb
    Dim dc As New DataClasses1DataContext
    Dim results = From emp In dc.Persons _
        Where TypeOf emp Is Employee _
        Select emp

    For Each Emp As Employee In results
        ListBox1.Items.Add(Emp.LastName)
    Next
    ```

    ```csharp
    NorthwindDataContext dc = new DataClasses1DataContext();
    var results = from emp in dc.Persons
                  where emp is Employee
                  select emp;

    foreach(Employee Emp in results)
    {
        listBox1.Items.Add(Emp.LastName)
    }
    ```

## <a name="test-the-application"></a>测试应用程序
 运行应用程序并验证是否显示在列表框中的记录是否全为员工 (具有值为 2 中的记录及其**类型**列)。

### <a name="to-test-the-application"></a>测试应用程序

1.  按 F5 。

2.  验证是否仅记录具有值为 2 在其**类型**显示列。

3.  关闭窗体。 (在**调试**菜单上，单击**停止调试**。)

## <a name="see-also"></a>请参阅

- [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [演练： 创建 LINQ to SQL 类 （O-R 设计器）](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [如何：分配存储过程以便执行更新、插入和删除操作（O/R 设计器）](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [如何： 在 Visual Basic 或 C# 中生成对象模型](/dotnet/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp)