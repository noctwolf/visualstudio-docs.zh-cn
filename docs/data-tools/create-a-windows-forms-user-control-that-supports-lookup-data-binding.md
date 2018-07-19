---
title: 在数据绑定的 Windows 窗体控件中使用查找表 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding, user controls
- LookupBindingPropertiesAttribute class, examples
- user controls [Visual Basic], creating
ms.assetid: c48b4d75-ccfc-4950-8b14-ff8adbfe4208
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: e79d4ba6db70876539aa2e85f0579953937cab14
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756319"
---
# <a name="create-a-windows-forms-user-control-that-supports-lookup-data-binding"></a>创建支持查找数据绑定的 Windows 窗体用户控件
在 Windows 窗体上显示数据，可以选择从现有控件**工具箱**，或如果你的应用程序需要标准控件中没有的功能，可以创作自定义控件。 本演练显示了如何创建实现 <xref:System.ComponentModel.LookupBindingPropertiesAttribute> 的控件。 实现 <xref:System.ComponentModel.LookupBindingPropertiesAttribute> 的控件可以包含三个属性，这些属性可以绑定到数据。 此类控件类似于 <xref:System.Windows.Forms.ComboBox>。

 控件创作的详细信息，请参阅[开发 Windows 窗体控件在设计时](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time)。

 创作用于数据绑定方案中的控件时，你需要实现以下数据绑定特性之一：

|数据绑定特性用法|
|-----------------------------------|
|在简单控件上实现 <xref:System.ComponentModel.DefaultBindingPropertyAttribute>（如 <xref:System.Windows.Forms.TextBox>），此类控件用于显示数据的单个列（或属性）。 有关详细信息，请参阅[创建支持简单数据绑定的 Windows 窗体用户控件](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md)。|
|在控件上实现 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>（如 <xref:System.Windows.Forms.DataGridView>），此类控件用于显示数据列表（或表）。 有关详细信息，请参阅[创建支持复杂数据绑定的 Windows 窗体用户控件](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)。|
|在控件上实现 <xref:System.ComponentModel.LookupBindingPropertiesAttribute>（如 <xref:System.Windows.Forms.ComboBox>），该控件用于显示数据列表（或表），也需要显示数据的单个列或属性。 （本演练页面描述了此过程）。|

 本演练创建绑定到源自两个表的数据的查找控件。 此示例使用源自 Northwind 示例数据库的 `Customers` 和 `Orders` 表。 查找控件绑定到`CustomerID`字段从`Orders`表。 使用此值来查找`CompanyName`从`Customers`表。

 在本演练中，你将学会如何执行以下任务：

-   创建一个新**Windows 窗体应用程序**。

-   添加一个新**用户控件**到你的项目。

-   以可视方式设计用户控件。

-   实现 `LookupBindingProperty` 特性。

-   创建具有的数据集**数据源配置**向导。

-   设置**CustomerID**上的列**订单**表，在**数据源**窗口中，若要使用新的控件。

-   创建一个用于在新控件中显示数据的窗体。

## <a name="prerequisites"></a>系统必备

本演练使用 SQL Server Express LocalDB 和 Northwind 示例数据库。

1.  如果您没有 SQL Server Express LocalDB，安装它从[SQL Server Express 下载页](https://www.microsoft.com/sql-server/sql-server-editions-express)，或通过**Visual Studio 安装程序**。 在中**Visual Studio 安装程序**，可以作为的一部分安装 SQL Server Express LocalDB**数据存储和处理**工作负荷，或作为单个组件。

2.  通过执行以下步骤安装 Northwind 示例数据库：

    1. 在 Visual Studio 中打开**SQL Server 对象资源管理器**窗口。 (SQL Server 对象资源管理器安装的一部分**数据存储和处理**Visual Studio 安装程序中的工作负载。)展开**SQL Server**节点。 LocalDB 实例上右键单击并选择**新查询**。

       查询编辑器窗口随即打开。

    2. 复制[Northwind Transact SQL 脚本](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true)到剪贴板。 此 T-SQL 脚本从零开始创建 Northwind 数据库，并使用数据填充它。

    3. 将 T-SQL 脚本粘贴到查询编辑器，然后选择**Execute**按钮。

       后不久，查询完成运行并创建 Northwind 数据库。

## <a name="create-a-windows-forms-application"></a>创建 Windows 窗体应用程序
 第一步是创建**Windows 窗体应用程序**。

#### <a name="to-create-the-new-windows-project"></a>创建新的 Windows 项目

1. 在 Visual Studio 中，在**文件**菜单中，选择**新建** > **项目**。

2. 展开**Visual C#** 或**Visual Basic**在左侧窗格中，然后选择**Windows 桌面**。

3. 在中间窗格中，选择**Windows 窗体应用**项目类型。

4. 将项目命名**LookupControlWalkthrough**，然后选择**确定**。

     **LookupControlWalkthrough**项目时创建，并添加到**解决方案资源管理器**。

## <a name="add-a-user-control-to-the-project"></a>将用户控件添加到项目
 本演练创建查找控件从**用户控件**，因此，添加**用户控件**项**LookupControlWalkthrough**项目。

#### <a name="to-add-a-user-control-to-the-project"></a>将用户控件添加到项目中

1.  从**项目**菜单中，选择**添加用户控件**。

2.  类型`LookupBox`中**名称**区域中，，然后单击**添加**。

     **LookupBox**控件添加到**解决方案资源管理器**，并在设计器中打开。

## <a name="design-the-lookupbox-control"></a>设计 LookupBox 控件

#### <a name="to-design-the-lookupbox-control"></a>设计 LookupBox 控件

-   拖动<xref:System.Windows.Forms.ComboBox>从**工具箱**到用户控件的设计图面。

## <a name="add-the-required-data-binding-attribute"></a>添加所需的数据绑定属性
 对于支持数据绑定的查找控件，你可以实现 <xref:System.ComponentModel.LookupBindingPropertiesAttribute>。

#### <a name="to-implement-the-lookupbindingproperties-attribute"></a>实现 LookupBindingProperties 特性

1.  交换机**LookupBox**到代码视图的控件。 (在**视图**菜单中，选择**代码**。)

2.  将 `LookupBox` 中的代码替换为以下内容：

     [!code-vb[VbRaddataDisplaying#5](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-lookup-data-binding_1.vb)]
     [!code-csharp[VbRaddataDisplaying#5](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-lookup-data-binding_1.cs)]

3.  从 **“生成”** 菜单中选择 **“生成解决方案”**。

## <a name="create-a-data-source-from-your-database"></a>从您的数据库创建数据源
此步骤中创建一个数据源使用**数据源配置**向导中，基于`Customers`和`Orders`Northwind 示例数据库中的表。

#### <a name="to-create-the-data-source"></a>创建数据源

1.  在 **“数据”** 菜单上，单击 **“显示数据源”**。

2.  在中**数据源**窗口中，选择**添加新数据源**以启动**数据源配置**向导。

3.  在 **“选择数据源类型”** 页上选择 **“数据库”** ，然后单击 **“下一步”**。

4.  上**选择您的数据连接**页面上执行以下项之一：

    -   如果下拉列表中包含到 Northwind 示例数据库的数据连接，请选择该连接。

    -   选择**新的连接**以启动**添加/修改连接**对话框。

5.  如果你的数据库需要密码，选择选项以包括敏感数据，然后单击**下一步**。

6.  上**将连接字符串保存到应用程序配置文件**页上，单击**下一步**。

7.  上**选择数据库对象**页上，展开**表**节点。

8.  选择`Customers`并`Orders`表，并单击**完成**。

     **NorthwindDataSet**添加到你的项目，并`Customers`并`Orders`表中出现**数据源**窗口。

## <a name="set-the-customerid-column-of-the-orders-table-to-use-the-lookupbox-control"></a>将订单表以使用 LookupBox 控件的客户 id 列设置
 内**数据源**窗口中，可以设置要在项拖动到窗体之前创建的控件。

#### <a name="to-set-the-customerid-column-to-bind-to-the-lookupbox-control"></a>将“CustomerID”列设置为绑定到 LookupBox 控件

1.  打开**Form1**在设计器中。

2.  展开**客户**中的节点**数据源**窗口。

3.  展开**订单**节点 (所示**客户**节点下**传真**列)。

4.  单击下拉箭头**订单**节点，然后选择**详细信息**从控件列表。

5.  单击下拉箭头**CustomerID**列 (在**订单**节点)，然后选择**自定义**。

6.  选择**LookupBox**从列表中**关联的控件**中**数据 UI 自定义选项**对话框。

7.  单击 **“确定”**。

8.  单击下拉箭头**CustomerID**列中，选择**LookupBox**。

## <a name="add-controls-to-the-form"></a>将控件添加到窗体
 可以通过将项从创建数据绑定控件**数据源**窗口拖到**Form1**。

#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>在 Windows 窗体上创建数据绑定控件

-   拖动**订单**从节点**数据源**窗口中的拖到 Windows 窗体，并验证**LookupBox**控件用于显示中的数据`CustomerID`列。

## <a name="bind-the-control-to-look-up-companyname-from-the-customers-table"></a>绑定控件从客户表中查找 CompanyName

#### <a name="to-setup-the-lookup-bindings"></a>设置查找绑定

-   选择主**客户**中的节点**数据源**窗口中，并将其放在组合框中框**CustomerIDLookupBox**上**Form1**.

     这将设置数据绑定显示`CompanyName`从`Customers`表，同时保持`CustomerID`值从`Orders`表。

## <a name="running-the-application"></a>运行应用程序

#### <a name="to-run-the-application"></a>要运行应用程序

-   按 **F5** 运行该应用程序。

-   导航某些记录，并确认`CompanyName`将出现在`LookupBox`控件。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)