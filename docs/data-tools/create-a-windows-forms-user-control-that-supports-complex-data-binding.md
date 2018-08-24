---
title: 使用数据绑定创建的 Windows 窗体用户控件
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding, user controls
- data binding, complex
- user controls [Visual Studio], complex data binding
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 11ab6a812701d371e86f07b3e8da5fa91f90cbcf
ms.sourcegitcommit: 3a11feebad45a0dd4ac45efcbfdf172fce46e1de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2018
ms.locfileid: "39582312"
---
# <a name="create-a-windows-forms-user-control-that-supports-complex-data-binding"></a>创建支持复杂数据绑定的 Windows 窗体用户控件

在 Windows 应用程序中的窗体上显示数据，可以选择从现有控件**工具箱**，或如果你的应用程序需要标准控件中不可用的功能，可以创作自定义控件。 本演练显示了如何创建实现 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> 的控件。 实现 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> 的控件包含可以绑定到数据的 `DataSource` 和 `DataMember` 属性。 此类控件类似于 <xref:System.Windows.Forms.DataGridView> 或 <xref:System.Windows.Forms.ListBox>。

控件创作的详细信息，请参阅[开发 Windows 窗体控件在设计时](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time)。

创建数据绑定方案中使用的控件时需要实现以下数据绑定特性之一：

|数据绑定特性用法|
|-----------------------------------|
|在简单控件上实现 <xref:System.ComponentModel.DefaultBindingPropertyAttribute>（如 <xref:System.Windows.Forms.TextBox>），此类控件用于显示数据的单个列（或属性）。 有关详细信息，请参阅[创建支持简单数据绑定的 Windows 窗体用户控件](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md)。|
|在控件上实现 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>（如 <xref:System.Windows.Forms.DataGridView>），此类控件用于显示数据列表（或表）。 （本演练页面描述了此过程）。|
|在控件上实现 <xref:System.ComponentModel.LookupBindingPropertiesAttribute>（如 <xref:System.Windows.Forms.ComboBox>），此类控件用于显示数据列表（或表），也需要显示数据的单个列或属性。 有关详细信息，请参阅[创建支持查找数据绑定的 Windows 窗体用户控件](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)。|

本演练创建显示表中多行数据的复杂控件。 本示例使用源自 Northwind 示例数据库的 `Customers` 表。 复杂用户控件将会在自定义控件中的 <xref:System.Windows.Forms.DataGridView> 中显示 Customers 表。

在本演练中，你将学会如何执行以下任务：

- 创建一个新**Windows 窗体应用程序**。

- 添加一个新**用户控件**到你的项目。

- 以可视方式设计用户控件。

- 实现 `ComplexBindingProperty` 特性。

- 创建具有的数据集[数据源配置向导](../data-tools/media/data-source-configuration-wizard.png)。

- 设置**客户**表中[数据源窗口](add-new-data-sources.md)以使用新的复杂控件。

- 通过将其从添加新控件**数据源窗口**拖动到**Form1**。

## <a name="prerequisites"></a>系统必备

本演练使用 SQL Server Express LocalDB 和 Northwind 示例数据库。

1. 如果您没有 SQL Server Express LocalDB，安装它从[SQL Server Express 下载页](https://www.microsoft.com/sql-server/sql-server-editions-express)，或通过**Visual Studio 安装程序**。 在中**Visual Studio 安装程序**，可以作为的一部分安装 SQL Server Express LocalDB**数据存储和处理**工作负荷，或作为单个组件。

1. 通过执行以下步骤安装 Northwind 示例数据库：

    1. 在 Visual Studio 中打开**SQL Server 对象资源管理器**窗口。 (SQL Server 对象资源管理器安装的一部分**数据存储和处理**Visual Studio 安装程序中的工作负载。)展开**SQL Server**节点。 LocalDB 实例上右键单击并选择**新查询**。

       查询编辑器窗口随即打开。

    1. 复制[Northwind Transact SQL 脚本](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true)到剪贴板。 此 T-SQL 脚本从零开始创建 Northwind 数据库，并使用数据填充它。

    1. 将 T-SQL 脚本粘贴到查询编辑器，然后选择**Execute**按钮。

       后不久，查询完成运行并创建 Northwind 数据库。

## <a name="create-a-windows-forms-application"></a>创建 Windows 窗体应用程序

第一步是创建**Windows 窗体应用程序**:

1. 在 Visual Studio 中，在**文件**菜单中，选择**新建** > **项目**。

1. 展开**Visual C#** 或**Visual Basic**在左侧窗格中，然后选择**Windows 桌面**。

1. 在中间窗格中，选择**Windows 窗体应用**项目类型。

1. 将项目命名**ComplexControlWalkthrough**，然后选择**确定**。

    **ComplexControlWalkthrough**项目时创建，并添加到**解决方案资源管理器**。

## <a name="add-a-user-control-to-the-project"></a>将用户控件添加到项目

因为本演练创建复杂数据绑定控件从**用户控件**，添加**用户控件**项与项目：

1. 从**项目**菜单中，选择**添加用户控件**。

1. 类型**ComplexDataGridView**中**名称**区域中，并单击**添加**。

    **ComplexDataGridView**控件添加到**解决方案资源管理器**，并在设计器中打开。

## <a name="design-the-complexdatagridview-control"></a>设计 ComplexDataGridView 控件

若要添加<xref:System.Windows.Forms.DataGridView>到用户控件中，拖动<xref:System.Windows.Forms.DataGridView>从**工具箱**到用户控件的设计图面。

## <a name="add-the-required-data-binding-attribute"></a>添加所需的数据绑定属性

对于复杂控件支持数据绑定的可以实现<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>:

1. 交换机**ComplexDataGridView**到代码视图的控件。 (在**视图**菜单中，选择**代码**。)

1. 将 `ComplexDataGridView` 中的代码替换为以下内容：

    [!code-csharp[VbRaddataDisplaying#4](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-complex-data-binding_1.cs)]
    [!code-vb[VbRaddataDisplaying#4](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-complex-data-binding_1.vb)]

1. 从 **“生成”** 菜单中选择 **“生成解决方案”**。

## <a name="create-a-data-source-from-your-database"></a>从您的数据库创建数据源

使用**数据源配置**向导创建数据源基于`Customers`Northwind 示例数据库中的表：

1.  在 **“数据”** 菜单上，单击 **“显示数据源”**。

2.  在中**数据源**窗口中，选择**添加新数据源**以启动**数据源配置**向导。

3.  在 **“选择数据源类型”** 页上选择 **“数据库”** ，然后单击 **“下一步”**。

4.  上**选择您的数据连接**页面上执行以下项之一：

    - 如果下拉列表中包含到 Northwind 示例数据库的数据连接，请选择该连接。

    - 选择**新的连接**以启动**添加/修改连接**对话框。

5.  如果你的数据库需要密码，选择选项以包括敏感数据，然后单击**下一步**。

6.  上**将连接字符串保存到应用程序配置文件**页上，单击**下一步**。

7.  上**选择数据库对象**页上，展开**表**节点。

8.  选择`Customers`表，并单击**完成**。

    **NorthwindDataSet**添加到你的项目，并`Customers`表中将出现**数据源**窗口。

## <a name="set-the-customers-table-to-use-the-complexdatagridview-control"></a>设置 Customers 表以使用 ComplexDataGridView 控件

内**数据源**窗口中，可以设置要在项拖动到窗体之前创建的控件：

1. 打开**Form1**在设计器中。

1. 展开**客户**中的节点**数据源**窗口。

1. 单击下拉箭头**客户**节点，然后选择**自定义**。

1. 选择**ComplexDataGridView**从列表中**关联的控件**中**数据 UI 自定义选项**对话框。

1. 单击下拉箭头`Customers`表，然后选择**ComplexDataGridView**从控件列表。

## <a name="add-controls-to-the-form"></a>将控件添加到窗体

可以通过将项从创建数据绑定控件**数据源**窗口拖到窗体上的。 将主**客户**从节点**数据源**拖到窗体的窗口。 确认**ComplexDataGridView**控件用于显示表的数据。

## <a name="run-the-application"></a>运行此应用程序

按 **F5** 运行该应用程序。

## <a name="next-steps"></a>后续步骤

根据应用程序的需求，在创建了支持数据绑定的控件后，还可能需要执行一些步骤。 接下来的一些常见步骤包括：

- 将你的自定义控件置于控件库中，以便在其他应用程序中重用它们。

- 创建支持查找方案的控件。 有关详细信息，请参阅[创建支持查找数据绑定的 Windows 窗体用户控件](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [设置从“数据源”窗口中拖动时要创建的控件](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)
- [Windows 窗体控件](/dotnet/framework/winforms/controls/index)