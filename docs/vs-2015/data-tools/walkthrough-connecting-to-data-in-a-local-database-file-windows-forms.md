---
title: 演练： 连接到本地数据库文件 （Windows 窗体） 中的数据 |Microsoft Docs
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
- databases, connecting to
- local data, SQL Express
- SQL Express, walkthroughs
- SQL Express, connecting
- data [Visual Studio], local
- data [Visual Studio], connecting to SQL Express
ms.assetid: 5e16b7da-3fdc-4e69-bdb4-e8e700481811
caps.latest.revision: 35
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 9b2d17c5ed86e37d3c674ef9238702cd8557a90f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482044"
---
# <a name="walkthrough-connecting-to-data-in-a-local-database-file-windows-forms"></a>演练：连接到本地数据库文件中的数据（Windows 窗体）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

通过创建数据集，然后将数据绑定控件添加到你的应用程序，可以快速轻松地在你的应用程序中显示本地数据库文件中的数据。 在本演练中，你将显示中的步骤创建本地数据库文件中的数据[通过使用设计器创建 SQL 数据库](../data-tools/create-a-sql-database-by-using-a-designer.md)。 创建 Windows 窗体项目后，你将连接到该数据库，并指定你希望 Customers 表中的数据显示在应用程序窗体上的数据网格中。  
  
 在 Visual Studio 2013 中创建数据库时，SQL Server Express LocalDB 引擎将用于访问 SQL Server 2012 中的数据库文件 (.mdf)。 在 Visual Studio 的早期版本中，SQL Server Express 引擎用于访问数据库文件 (.mdf)。 请参阅[本地数据概述](../data-tools/local-data-overview.md)。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
 本演练包含以下任务：  
  
-   [创建和配置数据集](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md#BKMK_CreateDataset)  
  
-   [添加数据绑定控件](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md#BKMK_AddCtrls)  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，需要访问通过完成创建的 SampleDatabase.mdf 数据库[通过使用设计器创建 SQL 数据库](../data-tools/create-a-sql-database-by-using-a-designer.md)。  
  
##  <a name="BKMK_CreateDataset"></a> 创建和配置数据集  
  
#### <a name="to-create-and-configure-a-dataset"></a>创建并配置数据集  
  
1.  创建 Windows 窗体项目，并将其命名**为 ConnectLocalData**。  
  
     请参阅[客户端应用程序](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)。  
  
2.  如果**数据源**窗口未出现，按 Shift Alt D 键，或在菜单栏上依次选择**视图**，**其他 Windows**，**显示数据源**.  
  
3.  在中**数据源**窗口中，选择**添加新数据源**链接。  
  
     在中**数据源配置向导**，选择**下一步**按钮两次以接受默认设置。  
  
4.  上**选择数据连接**页上，选择**新的连接**按钮。  
  
     **选择数据源**对话框随即出现。  
  
5.  在中**数据源**列表中，选择**Microsoft SQL Server 数据库文件**，然后选择**继续**按钮。  
  
     **添加连接**对话框随即出现。  
  
6.  在中**数据库文件的名称**框中，指定通过完成创建的文件[使用设计器创建 SQL 数据库](../data-tools/create-a-sql-database-by-using-a-designer.md)，或选择**浏览**按钮并找到该文件。  
  
     默认情况下，该文件位于用户\\*YourAccount*\Documents\Visual Studio*版本*\Projects\SampleDatabaseWalkthrough\SampleDatabaseWalkthrough。  
  
7.  下**登录到服务器**，接受默认值，选择**确定**按钮，，然后选择**下一步**按钮。  
  
    > [!NOTE]
    >  在连接到本地数据库文件时，可以在项目中创建该数据库的副本，也可以连接到位于该数据库当前位置的数据库文件。 请参阅[如何： 管理你的项目中的本地数据文件](../data-tools/how-to-manage-local-data-files-in-your-project.md)。  
  
8.  在出现的对话框中，选择**是**数据库文件复制到你的项目。  
  
9. 上**将连接字符串保存到应用程序配置文件**页上，选择**下一步**按钮。  
  
10. 上**选择数据库对象**页上，展开**表**节点中，选择**客户**并**订单**复选框，然后选择**完成**按钮。  
  
     **SampleDatabaseDataSet**添加到你的项目，并**客户**并**订单**表中出现**数据源**窗口。  
  
##  <a name="BKMK_AddCtrls"></a> 添加数据绑定控件  
  
#### <a name="to-add-data-bound-controls"></a>添加数据绑定控件  
  
1.  移动主**客户**从节点**数据源**窗口拖到**Form1**。  
  
     窗体上出现用于导航记录的 <xref:System.Windows.Forms.DataGridView> 和工具栏 (<xref:System.Windows.Forms.BindingNavigator>)。 一个[SampleDatabaseDataSet](../data-tools/dataset-tools-in-visual-studio.md)， [CustomersTableAdapter](../data-tools/tableadapter-overview.md)， <xref:System.Windows.Forms.BindingSource>，并<xref:System.Windows.Forms.BindingNavigator>组件栏中出现。  
  
2.  若要运行应用程序并显示你在上一个演练中添加的数据，请按 F5 键。  
  
3.  选择黄色添加图标 (![在 Windows 窗体中的添加按钮](../data-tools/media/addrecord.png "AddRecord"))，添加客户记录，并选择磁盘图标，然后保存所做的更改 (![在 Windows 窗体保存按钮](../data-tools/media/saveinwf.png "SaveInWF"))。  
  
4.  删除的记录，只需创建通过选择它，然后选择红色删除图标 (![在 Windows 窗体中的删除按钮](../data-tools/media/deleterecord.png "DeleteRecord"))。  
  
## <a name="next-steps"></a>后续步骤  
 可以创建或修改集中的对象，如果您打开中的数据源[创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)。 你还可以向该数据集中的数据表的 <xref:System.Data.DataTable.ColumnChanging> 或 <xref:System.Data.DataTable.RowChanging> 事件添加验证逻辑。 请参阅[验证数据集中](../data-tools/validate-data-in-datasets.md)。  
  
## <a name="see-also"></a>请参阅  
 [本地数据概述](../data-tools/local-data-overview.md)   
 [如何： 管理你的项目中的本地数据文件](../data-tools/how-to-manage-local-data-files-in-your-project.md)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)