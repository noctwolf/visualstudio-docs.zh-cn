---
title: 将 WPF 控件绑定到 WCF 数据服务
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio], walkthroughs
- WPF Designer, data binding
ms.assetid: 8823537c-82f0-41f7-bf30-705f0e5e59fd
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: b3cd83a16ff3d497bd9e6a46f3a66a3d99506a1f
ms.sourcegitcommit: 3a11feebad45a0dd4ac45efcbfdf172fce46e1de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2018
ms.locfileid: "39582390"
---
# <a name="bind-wpf-controls-to-a-wcf-data-service"></a>将 WPF 控件绑定到 WCF 数据服务

在本演练中，你将创建一个包含数据绑定控件的 WPF 应用程序。 这些控件将绑定到封装在 WCF 数据服务的客户记录。 你还将添加客户可用于查看和更新记录的按钮。

本演练阐释了以下任务：

- 创建一个利用 AdventureWorksLT 示例数据库中的数据生成的实体数据模型。

- 创建 WCF 数据服务公开实体数据模型与 WPF 应用程序中的数据。

- 通过将项从创建一组数据绑定控件**数据源**到 WPF 设计器窗口。

- 创建用于向前/向后导航客户记录的按钮。

- 创建一个按钮，将更改保存到 WCF 数据服务和基础数据源控件中的数据。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>系统必备

你需要以下组件来完成本演练：

-   Visual Studio

-   对附加了 AdventureWorksLT 示例数据库的 SQL Server 或 SQL Server Express 的正在运行的实例的访问权限。 您可以下载 AdventureWorksLT 数据库从[CodePlex 网站](http://go.microsoft.com/fwlink/?linkid=87843)。

事先了解以下概念也很有用，但对于完成本演练并不是必需的：

-   WCF 数据服务。 有关详细信息，请参阅[概述](/dotnet/framework/data/wcf/wcf-data-services-overview)。

-   [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] 中的数据模型。

-   实体数据模型和 ADO.NET 实体框架。 有关详细信息，请参阅[实体框架概述](/dotnet/framework/data/adonet/ef/overview)。

-   WPF 数据绑定。 有关详细信息，请参阅[数据绑定概述](/dotnet/framework/wpf/data/data-binding-overview)。

## <a name="create-the-service-project"></a>创建服务项目

开始本演练： 为 WCF 数据服务创建一个项目：

1.  启动 Visual Studio。

2.  在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“项目”**。

3.  展开**Visual C#** 或**Visual Basic**，然后选择**Web**。

4.  选择“ASP.NET Web 应用程序”项目模板。

5.  在中**名称**框中，键入**AdventureWorksService**然后单击**确定**。

     Visual Studio 将创建**AdventureWorksService**项目。

6.  在中**解决方案资源管理器**，右键单击**Default.aspx** ，然后选择**删除**。 本演练中不需要此文件。

## <a name="create-an-entity-data-model-for-the-service"></a>创建实体数据模型服务

若要使用的 WCF 数据服务公开的应用程序的数据，必须定义服务的数据模型。 WCF 数据服务支持两种类型的数据模型： 实体数据模型和使用实现的公共语言运行时 (CLR) 对象定义的自定义数据模型<xref:System.Linq.IQueryable%601>接口。 在本演练中，你将为该数据模型创建一个实体数据模型。

1.  在 **“项目”** 菜单上，单击 **“添加新项”**。

2.  在已安装的模板列表中，单击**数据**，然后选择**ADO.NET 实体数据模型**项目项。

3.  将名称更改为`AdventureWorksModel.edmx`，然后单击**添加**。

     **实体数据模型**向导随即打开。

4.  上**选择模型内容**页上，单击**从数据库生成**，然后单击**下一步**。

5.  上**选择数据连接**页上，选择以下选项之一：

    -   如果下拉列表中包含到 AdventureWorksLT 示例数据库的数据连接，请选择该连接。

    -   单击**新的连接**，并创建与 AdventureWorksLT 数据库的连接。

6.  上**选择数据连接**页上，请确保**将实体连接设置保存在 App.Config 作为**选项已选中，然后单击**下一步**。

7.  上**选择数据库对象**页上，展开**表**，然后选择**SalesOrderHeader**表。

8.  单击 **“完成”**。

## <a name="create-the-service"></a>创建服务

创建 WCF 数据服务公开实体数据模型与 WPF 应用程序中的数据：

1.  上**项目**菜单中，选择**添加新项**。

2.  在中**已安装的模板**列表中，单击**Web**，然后选择**WCF 数据服务**项目项。

3.  在中**名称**框中，键入`AdventureWorksService.svc`，然后单击**添加**。

     Visual Studio 将添加`AdventureWorksService.svc`到项目。

## <a name="configure-the-service"></a>配置服务

必须配置要在您创建的实体数据模型上运行的服务：

1.  在中`AdventureWorks.svc`代码文件中，替换**AdventureWorksService**类声明替换下面的代码。

     [!code-csharp[Data_WPFWCF#1](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_1.cs)]
     [!code-vb[Data_WPFWCF#1](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_1.vb)]

     此代码将更新**AdventureWorksService**类，以便它派生<xref:System.Data.Services.DataService%601>它`AdventureWorksLTEntities`对象实体数据模型中的上下文类。 此代码还将更新 `InitializeService` 方法，以使服务的客户端具有对 `SalesOrderHeader` 实体的完全读/写访问权限。

2.  生成项目，并确认生成过程中未发生错误。

## <a name="create-the-wpf-client-application"></a>创建 WPF 客户端应用程序

若要显示来自 WCF 数据服务的数据，请使用基于服务的数据源创建新的 WPF 应用程序。 在本演练后面的部分中，你将向该应用程序中添加数据绑定控件。

1.  在中**解决方案资源管理器**，右键单击解决方案节点，单击**添加**，然后选择**新项目**。

2.  在中**新的项目**对话框中，展开**Visual C#** 或**Visual Basic**，然后选择**Windows**。

3.  选择**WPF 应用程序**项目模板。

4.  在中**名称**框中，键入`AdventureWorksSalesEditor`，然后单击**确定**。

     Visual Studio 将添加`AdventureWorksSalesEditor`到解决方案。

5.  在 **“数据”** 菜单上，单击 **“显示数据源”**。

     **数据源**窗口随即打开。

6.  在 **“数据源”** 窗口中，单击 **“添加新数据源”**。

     **数据源配置**向导随即打开。

7.  在中**选择数据源类型**页的向导中，选择**服务**，然后单击**下一步**。

8.  在中**添加服务引用**对话框中，单击**Discover**。

     Visual Studio 中搜索可用服务的当前解决方案，并将添加`AdventureWorksService.svc`中可用的服务的列表**Services**框。

9. 在中**Namespace**框中，键入**AdventureWorksService**。

10. 在中**Services**框中，单击**AdventureWorksService.svc**，然后单击**确定**。

     Visual Studio 下载服务信息，然后返回到**数据源配置**向导。

11. 在中**添加服务引用**页上，单击**完成**。

     Visual Studio 将添加到该服务返回的数据表示的节点**数据源**窗口。

## <a name="define-the-user-interface"></a>定义用户界面

通过在 WPF 设计器中修改 XAML，将多个按钮添加到该窗口中。 在本演练后面的部分中，你将添加可让用户通过使用这些按钮来查看和更新销售记录的代码。

1.  在中**解决方案资源管理器**，双击**MainWindow.xaml**。

     将在 WPF 设计器中打开相应的窗口。

2.  在设计器的 [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] 视图中，在 `<Grid>` 标记之间添加以下代码：

    ```xaml
    <Grid.RowDefinitions>
        <RowDefinition Height="75" />
        <RowDefinition Height="525" />
    </Grid.RowDefinitions>
    <Button HorizontalAlignment="Left" Margin="22,20,0,24" Name="backButton" Width="75"><</Button>
    <Button HorizontalAlignment="Left" Margin="116,20,0,24" Name="nextButton" Width="75">></Button>
    <Button HorizontalAlignment="Right" Margin="0,21,46,24" Name="saveButton" Width="110">Save changes</Button>
    ```

3.  生成项目。

## <a name="create-the-data-bound-controls"></a>创建数据绑定控件

创建通过拖动显示客户记录的控件`SalesOrderHeaders`节点从**数据源**到设计器窗口。

1.  在中**数据源**窗口中，单击下拉列表菜单**SalesOrderHeaders**节点，然后选择**详细信息**。

2.  展开**SalesOrderHeaders**节点。

3.  对于此示例中，某些字段将不会显示，因此单击以下节点旁边的下拉列表菜单并选择**None**:

    -   **CreditCardApprovalCode**

    -   **ModifiedDate**

    -   **类型 OnlineOrderFlag**

    -   **RevisionNumber**

    -   **rowguid**

    此操作将阻止 Visual Studio 在下一步中为这些节点创建数据绑定控件。 本演练中，假设，最终用户不需要查看此数据。

4.  从**数据源**窗口中，拖动**SalesOrderHeaders**到位于包含按钮的行下方的网格行的节点。

     Visual Studio 生成 XAML 和代码创建一组中的数据绑定的控件**产品**表。 有关生成的 XAML 和代码的详细信息，请参阅[控件添加到 Visual Studio 中的数据绑定 WPF](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)。

5.  在设计器中，单击文本框旁边**客户 ID**标签。

6.  在中**属性**窗口中，选择旁边的复选框**IsReadOnly**属性。

7.  设置**IsReadOnly**以下文本框中的每个属性：

    -   **采购订单号**

    -   **销售订单 ID**

    -   **销售订单号**

## <a name="load-the-data-from-the-service"></a>从服务加载数据

使用服务代理对象从服务加载销售数据。 然后将返回的数据分配给数据源<xref:System.Windows.Data.CollectionViewSource>WPF 窗口中。

1.  在设计器来创建`Window_Loaded`事件处理程序中，双击读取的文本： **MainWindow**。

2.  将该事件处理程序替换为以下代码。 请确保您替换*localhost*地址在此代码与在开发计算机上的本地主机地址。

     [!code-csharp[Data_WPFWCF#2](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_2.cs)]
     [!code-vb[Data_WPFWCF#2](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_2.vb)]

## <a name="navigate-sales-records"></a>导航销售记录

添加代码，使用户能够通过使用滚动销售记录**\<** 并**>** 按钮。

1.  在设计器中，双击**<** 窗口图面上的按钮。

     Visual Studio 将打开代码隐藏文件，并创建一个新`backButton_Click`事件处理程序<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件。

2.  将以下代码添加到生成的 `backButton_Click` 事件处理程序中：

     [!code-csharp[Data_WPFWCF#3](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_3.cs)]
     [!code-vb[Data_WPFWCF#3](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_3.vb)]

3.  返回到设计器中，并双击**>** 按钮。

     Visual Studio 将打开代码隐藏文件，并创建一个新`nextButton_Click`事件处理程序<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件。

4.  将以下代码添加到生成的 `nextButton_Click` 事件处理程序中：

     [!code-csharp[Data_WPFWCF#4](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_4.cs)]
     [!code-vb[Data_WPFWCF#4](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_4.vb)]

## <a name="save-changes-to-sales-records"></a>保存对销售记录的更改

添加代码，使用户能够查看和保存对销售记录的更改，通过使用**保存更改**按钮：

1.  在设计器中，双击**保存更改**按钮。

     Visual Studio 将打开代码隐藏文件，并创建一个新`saveButton_Click`事件处理程序<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件。

2.  将以下代码添加到 `saveButton_Click` 事件处理程序中。

     [!code-csharp[Data_WPFWCF#5](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-wcf-data-service_5.cs)]
     [!code-vb[Data_WPFWCF#5](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-wcf-data-service_5.vb)]

## <a name="test-the-application"></a>测试应用程序

生成并运行应用程序以验证你可以查看和更新客户记录：

1.  上**构建**菜单上，单击**生成解决方案**。 验证解决方案已生成且未发生错误。

2.  按**Ctrl**+**F5**。

     Visual Studio 将启动**AdventureWorksService**项目，而不进行调试。

3.  在中**解决方案资源管理器**，右键单击**AdventureWorksSalesEditor**项目。

4.  在上下文菜单中下,**调试**，单击**启动新实例**。

     将运行应用程序。 验证以下内容：

    -   文本框中显示的数据的销售订单 id 的第一个销售记录的不同字段**71774**。

    -   可以单击**>** 或**<** 按钮来导航其他销售记录。

5.  在其中一个销售记录中, 键入一些文本**注释**框中，然后依次**保存更改**。

6.  关闭应用程序，然后从 Visual Studio 中再次启动该应用程序。

7.  导航到所更改的销售记录，然后验证相关更改是否在你关闭并重新打开应用程序后得以保留。

8.  关闭该应用程序。

## <a name="next-steps"></a>后续步骤

完成本演练后，你可以执行以下相关任务：

-   了解如何使用**数据源**窗口在 Visual Studio 中将 WPF 控件添加到其他类型的数据源。 有关详细信息，请参阅[绑定 WPF 控件添加到数据集](../data-tools/bind-wpf-controls-to-a-dataset.md)。

-   了解如何使用**数据源**在 WPF 控件中显示相关的数据 （即，在父-子关系中的数据） 的 Visual Studio 窗口中。 有关详细信息，请参阅[演练： 在 WPF 应用程序中显示相关的数据](../data-tools/display-related-data-in-wpf-applications.md)。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中将 WPF 控件绑定到数据](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [将 WPF 控件绑定到数据集](../data-tools/bind-wpf-controls-to-a-dataset.md)
- [WCF 概述 (.NET Framework)](/dotnet/framework/data/wcf/wcf-data-services-overview)
- [实体框架概述 (.NET Framework)](/dotnet/framework/data/adonet/ef/overview)
- [数据绑定概述 (.NET Framework)](/dotnet/framework/wpf/data/data-binding-overview)