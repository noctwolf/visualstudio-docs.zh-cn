---
title: 将 WPF 控件绑定到数据集 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio], walkthroughs
- WPF Designer, data binding
ms.assetid: 177420b9-568b-4dad-9d16-1b0e98a24d71
caps.latest.revision: 35
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8e04e8ec9ae181a7cb894b22efecab0ad6ba68b7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483702"
---
# <a name="bind-wpf-controls-to-a-dataset"></a>将 WPF 控件绑定到数据集
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[绑定 WPF 控件添加到数据集](https://docs.microsoft.com/visualstudio/data-tools/bind-wpf-controls-to-a-dataset)。  
  
  
在本演练中，你将创建一个包含数据绑定控件的 WPF 应用程序。 这些控件将绑定到在数据集中封装的产品记录。 你还将添加用于浏览产品和保存对产品记录所做的更改的按钮。  
  
 本演练阐释了以下任务：  
  
-   创建一个 WPF 应用程序和一个利用 AdventureWorksLT 示例数据库中的数据生成的数据集。  
  
-   通过将数据从表创建数据绑定控件的一组**数据源**到 WPF 设计器中的窗口的窗口。  
  
-   创建用于向前/向后导航产品记录的按钮。  
  
-   创建一个用于将用户对产品记录所做的更改保存到数据表和基础数据源的按钮。  
  
     [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>系统必备  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]  
  
-   对附加了 AdventureWorksLT 示例数据库的 SQL Server 或 SQL Server Express 的正在运行的实例的访问权限。 您可以下载 AdventureWorksLT 数据库从[CodePlex 网站上](http://go.microsoft.com/fwlink/?linkid=87843)。  
  
 事先了解以下概念也很有用，但对于完成本演练并不是必需的：  
  
-   数据集和 TableAdapter。 有关详细信息，请参阅[Visual Studio 中的数据集工具](../data-tools/dataset-tools-in-visual-studio.md)并[TableAdapter 概述](../data-tools/tableadapter-overview.md)。  
  
-   使用 WPF 设计器。 有关详细信息，请参阅[WPF 和 Silverlight 设计器概述](http://msdn.microsoft.com/en-us/570b7a5c-0c86-4326-a371-c9b63378fc62)。  
  
-   WPF 数据绑定。 有关详细信息，请参阅 [数据绑定概述](http://msdn.microsoft.com/library/c707c95f-7811-401d-956e-2fffd019a211)。  
  
## <a name="create-the-project"></a>创建项目  
 创建一个新的 WPF 项目。 该项目将显示产品记录。  
  
#### <a name="to-create-the-project"></a>创建项目  
  
1.  启动 Visual Studio。  
  
2.  在 **“文件”** 菜单上，指向 **“新建”**，然后单击 **“项目”**。  
  
3.  展开**Visual Basic**或**Visual C#**，然后选择**Windows**。  
  
4.  选择**WPF 应用程序**项目模板。  
  
5.  在中**名称**框中，键入`AdventureWorksProductsEditor`然后单击**确定**。  
  
     Visual Studio 将创建`AdventureWorksProductsEditor`项目。  
  
## <a name="create-a-dataset-for-the-application"></a>创建应用程序的数据集  
 您可以创建数据绑定控件之前，必须为应用程序定义数据模型并将其添加到**数据源**窗口。 在本演练中，你将创建要用作数据模型的数据集。  
  
#### <a name="to-create-a-dataset"></a>创建数据集  
  
1.  在 **“数据”** 菜单上，单击 **“显示数据源”**。  
  
     **数据源**窗口随即打开。  
  
2.  在 **“数据源”** 窗口中，单击 **“添加新数据源”**。  
  
     **数据源配置**向导随即打开。  
  
3.  上**选择数据源类型**页上，选择**数据库**，然后单击**下一步**。  
  
4.  上**选择数据库模型**页上，选择**数据集**，然后单击**下一步**。  
  
5.  上**选择数据连接**页上，选择以下选项之一：  
  
    -   如果下拉列表中有到 AdventureWorksLT 示例数据库的数据连接，则选择它，然后单击**下一步**。  
  
    -   单击**新的连接**，并创建与 AdventureWorksLT 数据库的连接。  
  
6.  上**将连接字符串保存到应用程序配置文件**页上，选择**是，保存所用连接**复选框，然后依次**下一步**。  
  
7.  上**选择数据库对象**页上，展开**表**，然后选择**Product (SalesLT)** 表。  
  
8.  单击 **“完成”**。  
  
     Visual Studio 将新的 AdventureWorksLTDataSet.xsd 文件添加到项目中，并添加相应**adventureworksltdataset**项**数据源**窗口。 AdventureWorksLTDataSet.xsd 文件定义了一个名为 `AdventureWorksLTDataSet` 的类型化数据集和一个名为 `ProductTableAdapter` 的 TableAdapter。 在本演练后面的部分中，你将使用 `ProductTableAdapter` 向数据集填充数据，并将更改保存回数据库中。  
  
9. 生成项目。  
  
## <a name="edit-the-default-fill-method-of-the-tableadapter"></a>编辑 TableAdapter 的默认填充方法  
 若要向数据集填充数据，请使用 `Fill` 的 `ProductTableAdapter` 方法。 默认情况下，`Fill` 方法将向 `ProductDataTable` 中的 `AdventureWorksLTDataSet` 填充 Product 表包含的所有数据行。 你可以修改此方法以仅返回行的子集。 对于本演练而言，将修改 `Fill` 方法以仅返回具有照片的产品行。  
  
#### <a name="to-load-product-rows-that-have-photos"></a>加载具有照片的产品行  
  
1.  在中**解决方案资源管理器**，双击 AdventureWorksLTDataSet.xsd 文件。  
  
     这将打开数据集设计器。  
  
2.  在设计器中，右键单击**Fill,GetData()** 查询，然后选择**配置**。  
  
     **TableAdapter 配置**向导随即打开。  
  
3.  在中**输入 SQL 语句**页上，添加以下 WHERE 子句之后`SELECT`在文本框中的语句。  
  
    ```  
    WHERE ThumbnailPhotoFileName <> 'no_image_available_small.gif'  
    ```  
  
4.  单击 **“完成”**。  
  
## <a name="define-the-user-interface"></a>定义用户界面  
 通过在 WPF 设计器中修改 XAML，将多个按钮添加到该窗口中。 在本演练后面的部分中，你将添加可让用户通过使用这些按钮来滚动和保存对产品记录所做的更改的代码。  
  
#### <a name="to-define-the-user-interface-of-the-window"></a>定义窗口的用户界面  
  
1.  在中**解决方案资源管理器**，双击 MainWindow.xaml。  
  
     将在 WPF 设计器中打开相应的窗口。  
  
2.  在设计器的 [!INCLUDE[TLA#tla_titlexaml](../includes/tlasharptla-titlexaml-md.md)] 视图中，在 `<Grid>` 标记之间添加以下代码：  
  
    ```  
    <Grid.RowDefinitions>  
        <RowDefinition Height="75" />  
        <RowDefinition Height="625" />  
    </Grid.RowDefinitions>  
    <Button HorizontalAlignment="Left" Margin="22,20,0,24" Name="backButton" Width="75"><</Button>  
    <Button HorizontalAlignment="Left" Margin="116,20,0,24" Name="nextButton" Width="75">></Button>  
    <Button HorizontalAlignment="Right" Margin="0,21,46,24" Name="saveButton" Width="110">Save changes</Button>  
    ```  
  
3.  生成项目。  
  
## <a name="createdata-bound-controls"></a>可以绑定控件  
 创建通过拖动显示客户记录的控件`Product`表从**数据源**到 WPF 设计器窗口。  
  
#### <a name="to-create-data-bound-controls"></a>创建数据绑定控件  
  
1.  在中**数据源**窗口中，单击下拉列表菜单**产品**节点，然后选择**详细信息**。  
  
2.  展开**产品**节点。  
  
3.  对于此示例中，某些字段将不会显示，因此单击以下节点旁边的下拉列表菜单并选择**None**:  
  
    -   ProductCategoryID  
  
    -   ProductModelID  
  
    -   ThumbnailPhotoFileName  
  
    -   rowguid  
  
    -   ModifiedDate  
  
4.  单击下拉列表菜单旁边**ThumbNailPhoto**节点，然后选择**映像**。  
  
    > [!NOTE]
    >  默认情况下中的项**数据源**表示图片的窗口已设置为其默认控件**None**。 这是因为，图片是作为字节数组存储在数据库中的，并且从简单的字节数组到大型应用程序的可执行文件都可以包含在字节数组中。  
  
5.  从**数据源**窗口中，拖动**产品**到位于包含按钮的行下方的网格行的节点。  
  
     Visual Studio 将生成定义一组中的数据绑定的控件的 XAML**产品**表。 它还会生成用于加载数据的代码。 有关生成的 XAML 和代码的详细信息，请参阅[控件添加到 Visual Studio 中的数据绑定 WPF](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)。  
  
6.  在设计器中，单击文本框旁边**产品 ID**标签。  
  
7.  在中**属性**窗口中，选择旁边的复选框**IsReadOnly**属性。  
  
## <a name="navigating-product-records"></a>导航产品记录  
 添加代码，使用户能够滚动产品记录通过使用**\<** 并**>** 按钮。  
  
#### <a name="to-enable-users-to-navigate-product-records"></a>使用户能够导航产品记录  
  
1.  在设计器中，双击**<** 窗口图面上的按钮。  
  
     Visual Studio 将打开代码隐藏文件，并创建一个新`backButton_Click`事件处理程序<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件。  
  
2.  修改`Window_Loaded`事件处理程序，因此`ProductViewSource`， `AdventureWorksLTDataSet`，和`AdventureWorksLTDataSetProductTableAdapter`是外部方法和可以访问整个窗体。 声明仅这些测试是全局的窗体，并将其内分配`Window_Loaded`事件处理程序如下所示：  
  
     [!code-csharp[Data_WPFDATASET#1](../snippets/csharp/VS_Snippets_ProTools/data_wpfdataset/cs/mainwindow.xaml.cs#1)]
     [!code-vb[Data_WPFDATASET#1](../snippets/visualbasic/VS_Snippets_ProTools/data_wpfdataset/vb/mainwindow.xaml.vb#1)]  
  
3.  将以下代码添加到 `backButton_Click` 事件处理程序中：  
  
     [!code-csharp[Data_WPFDATASET#2](../snippets/csharp/VS_Snippets_ProTools/data_wpfdataset/cs/mainwindow.xaml.cs#2)]
     [!code-vb[Data_WPFDATASET#2](../snippets/visualbasic/VS_Snippets_ProTools/data_wpfdataset/vb/mainwindow.xaml.vb#2)]  
  
4.  返回到设计器，然后双击**>** 按钮。  
  
5.  将以下代码添加到 `nextButton_Click` 事件处理程序中：  
  
     [!code-csharp[Data_WPFDATASET#3](../snippets/csharp/VS_Snippets_ProTools/data_wpfdataset/cs/mainwindow.xaml.cs#3)]
     [!code-vb[Data_WPFDATASET#3](../snippets/visualbasic/VS_Snippets_ProTools/data_wpfdataset/vb/mainwindow.xaml.vb#3)]  
  
## <a name="savechanges-to-product-records"></a>对产品记录的 Savechanges  
 添加代码，使用户能够保存的更改对产品记录通过使用**保存更改**按钮。  
  
#### <a name="to-add-the-ability-to-save-changes-to-product-records"></a>添加保存对产品记录所做更改的功能  
  
1.  在设计器中，双击**保存更改**按钮。  
  
     Visual Studio 将打开代码隐藏文件，并创建一个新`saveButton_Click`事件处理程序<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件。  
  
2.  将以下代码添加到 `saveButton_Click` 事件处理程序中：  
  
     [!code-csharp[Data_WPFDATASET#4](../snippets/csharp/VS_Snippets_ProTools/data_wpfdataset/cs/mainwindow.xaml.cs#4)]
     [!code-vb[Data_WPFDATASET#4](../snippets/visualbasic/VS_Snippets_ProTools/data_wpfdataset/vb/mainwindow.xaml.vb#4)]  
  
    > [!NOTE]
    >  此示例使用 `Save` 的 `TableAdapter` 方法来保存更改。 这对于本演练很合适，因为本演练中只会更改一个数据表。 如果你需要保存对多个数据表所做的更改，则还可以使用 Visual Studio 利用你的数据集生成的 `UpdateAll` 的 `TableAdapterManager` 方法。 有关详细信息，请参阅[TableAdapterManager 概述](http://msdn.microsoft.com/library/33076d42-6b41-491a-ac11-6c6339aea650)。  
  
## <a name="test-the-application"></a>测试应用程序  
 生成并运行应用程序。 验证你是否可以查看和更新产品记录。  
  
#### <a name="to-test-the-application"></a>测试应用程序  
  
1.  按 F5 。  
  
     这将生成并运行应用程序。 验证以下内容：  
  
    -   文本框显示具有图片的第一条产品记录的数据。 此产品，并且在产品 ID 为 713，名称**Long-sleeve Logo Jersey，S**。  
  
    -   可以单击**>** 或**<** 按钮来导航其他产品记录。  
  
2.  在其中一个产品记录，更改**大小**值，然后依次**保存更改**。  
  
3.  关闭该应用程序，并按下然后重新启动该应用程序**F5** Visual Studio 中。  
  
4.  导航到已更改的产品记录，然后验证是否已保存更改。  
  
5.  关闭该应用程序。  
  
## <a name="next-steps"></a>后续步骤  
 完成本演练后，你可以执行以下相关任务：  
  
-   了解如何使用**数据源**窗口在 Visual Studio 中将 WPF 控件添加到其他类型的数据源。 有关详细信息，请参阅[绑定 WPF 控件添加到 WCF 数据服务](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)。  
  
-   了解如何使用**数据源**在 WPF 控件中显示相关的数据 （即，在父-子关系中的数据） 的 Visual Studio 窗口中。 有关详细信息，请参阅[演练： 在 WPF 应用程序中显示相关数据](../data-tools/walkthrough-displaying-related-data-in-a-wpf-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [将 WPF 控件绑定到 Visual Studio 中的数据](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)   
 [将 WPF 控件绑定到 Visual Studio 中的数据](../data-tools/bind-wpf-controls-to-data-in-visual-studio2.md)   
 [Visual Studio 中的数据集工具](../data-tools/dataset-tools-in-visual-studio.md)   
 [WPF 和 Silverlight 设计器概述](http://msdn.microsoft.com/en-us/570b7a5c-0c86-4326-a371-c9b63378fc62)   
 [数据绑定概述](http://msdn.microsoft.com/library/c707c95f-7811-401d-956e-2fffd019a211)

