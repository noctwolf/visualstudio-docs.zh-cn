---
title: 创建用于搜索数据的 Windows 窗体
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Windows Forms, searching data
- Windows Forms, displaying data
- parameters, displaying filtered data
- data [Visual Studio], parameterizing queries
- data [Visual Studio], searching
ms.assetid: 65ca79a9-7458-466c-af55-978cd24c549e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: cdc82db1f701abb26b983fe0a1f2e4c7752c6c55
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756394"
---
# <a name="create-a-windows-form-to-search-data"></a>创建用于搜索数据的 Windows 窗体
一个常见的应用程序方案是显示窗体上选择的数据。 例如，你可能希望显示特定客户的订单或特定订单的详细信息。 在本方案中，用户向窗体输入信息，然后以用户的输入作为参数执行查询，即基于参数化查询来选择数据。 查询只返回符合用户输入的条件的数据。 本演练显示了如何创建返回特定城市中客户的查询，并修改用户界面，以便用户可以输入城市名称并按按钮以执行该查询。

 通过让数据库执行其最擅长的工作（即快速筛选记录），使用参数化查询有助于使你的应用程序更有效。 与此相反，如果你请求整个数据库表、 在网络上传输它，然后使用应用程序逻辑以查找所需的记录，你的应用程序将变慢且效率低下。

 可以将参数化的查询添加到任何 TableAdapter （和控件以接受参数值并执行查询），使用**搜索标准生成器**对话框。 通过选择打开的对话框**添加查询**命令**数据**菜单 （或任何 TableAdapter 智能标记）。

 本演练涉及以下任务：

-   创建一个新**Windows 窗体应用程序**项目。

-   创建和使用应用程序中配置数据源**数据源配置**向导。

-   设置中的项的拖放类型**数据源**窗口。

-   创建通过将项从显示数据的控件**数据源**拖到窗体的窗口。

-   添加用于在窗体上显示数据的控件。

-   完成**搜索标准生成器**对话框。

-   在窗体中输入参数和执行参数化的查询。

## <a name="prerequisites"></a>系统必备

本演练使用 SQL Server Express LocalDB 和 Northwind 示例数据库。

1.  如果您没有 SQL Server Express LocalDB，安装它从[SQL Server Express 下载页](https://www.microsoft.com/sql-server/sql-server-editions-express)，或通过**Visual Studio 安装程序**。 在中**Visual Studio 安装程序**，你可以安装 SQL Server Express LocalDB 作为的一部分**数据存储和处理**工作负荷，或作为单个组件。

2.  通过执行以下步骤安装 Northwind 示例数据库：

    1. 在 Visual Studio 中打开**SQL Server 对象资源管理器**窗口。 (SQL Server 对象资源管理器安装的一部分**数据存储和处理**中的工作负荷**Visual Studio 安装程序**。)展开**SQL Server**节点。 LocalDB 实例上右键单击并选择**新查询**。

       查询编辑器窗口随即打开。

    2. 复制[Northwind Transact SQL 脚本](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true)到剪贴板。 此 T-SQL 脚本从零开始创建 Northwind 数据库，并使用数据填充它。

    3. 将 T-SQL 脚本粘贴到查询编辑器，然后选择**Execute**按钮。

       后不久，查询完成运行并创建 Northwind 数据库。

## <a name="create-the-windows-forms-application"></a>创建 Windows 窗体应用程序
 第一步是创建**Windows 窗体应用程序**。 向项目分配名称是可选的在此步骤中，但您将为其命名此处因为会将项目保存更高版本。

#### <a name="to-create-the-new-windows-forms-application-project"></a>若要创建新的 Windows 窗体应用程序项目

1. 在 Visual Studio 中，在**文件**菜单中，选择**新建** > **项目**。

2. 展开**Visual C#** 或**Visual Basic**在左侧窗格中，然后选择**Windows 桌面**。

3. 在中间窗格中，选择**Windows 窗体应用**项目类型。

4. 将项目命名**WindowsSearchForm**，然后选择**确定**。

     **WindowsSearchForm**创建项目并将其添加到**解决方案资源管理器**。

## <a name="create-the-data-source"></a>创建数据源
此步骤将创建从数据库使用的数据源**数据源配置**向导。

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

8.  选择**客户**表，并单击**完成**。

     **NorthwindDataSet**添加到你的项目，并**客户**表中将显示**数据源**窗口。

## <a name="create-the-form"></a>创建窗体
 可以通过将项从创建数据绑定控件**数据源**窗口拖到窗体上的。

#### <a name="to-create-data-bound-controls-on-the-form"></a>在窗体上创建数据绑定控件

1.  展开**客户**中的节点**数据源**窗口。

2.  拖动**客户**从节点**数据源**向窗体的窗口。

     窗体上出现用于导航记录的 <xref:System.Windows.Forms.DataGridView> 和工具栏 (<xref:System.Windows.Forms.BindingNavigator>)。 一个[NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)，CustomersTableAdapter <xref:System.Windows.Forms.BindingSource>，和<xref:System.Windows.Forms.BindingNavigator>组件栏中出现。

## <a name="add-parameterization-search-functionality-to-the-query"></a>向查询添加参数化 （搜索功能）
 可以将 WHERE 子句添加到原始查询使用**搜索标准生成器**对话框。

#### <a name="to-create-a-parameterized-query-and-controls-to-enter-the-parameters"></a>创建参数化查询和用于输入参数的控件

1.  选择<xref:System.Windows.Forms.DataGridView>控件，然后再选择**添加查询**上**数据**菜单。

2.  类型`FillByCity`中**新的查询名称**上的区域**搜索标准生成器**对话框。

3.  添加`WHERE City = @City`中对该查询**查询文本**区域。

     查询应当类似于：

     ```sql
     SELECT CustomerID, CompanyName, ContactName, ContactTitle,
          Address, City, Region, PostalCode, Country, Phone, Fax
     FROM Customers
     WHERE City = @City
     ```

    > [!NOTE]
    >  访问和 OLE DB 数据源使用问号 (？) 表示参数，因此在 WHERE 子句将类似如下： `WHERE City = ?`。

4.  单击**确定**以关闭**搜索标准生成器**对话框。

     一个**FillByCityToolStrip**添加到窗体。

## <a name="testing-the-application"></a>测试应用程序
 运行应用程序将打开你的窗体，并使其准备好接收作为输入参数。

#### <a name="to-test-the-application"></a>测试应用程序

1.  按 **F5** 运行该应用程序。

2.  类型**伦敦**成**市/县**文本框中，，然后单击**FillByCity**。

     符合条件的客户使用填充数据网格。 在此示例中，数据网格只显示具有值的客户**伦敦**在其**城市**列。

## <a name="next-steps"></a>后续步骤
 根据应用程序的需求，在创建参数化窗体后可能还需要执行一些步骤。 你可以通过以下操作来增强此演练的效果：

-   添加显示相关数据的控件。 有关详细信息，请参阅[中的数据集的关系](relationships-in-datasets.md)。

-   编辑数据集来添加或移除数据库对象。 有关详细信息，请参阅[创建和配置数据集](../data-tools/create-and-configure-datasets-in-visual-studio.md)。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)