---
title: 演练： 使用数据集设计器创建数据集 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
- datasets [Visual Basic], walkthroughs
- XML schemas, creating datasets
- data [Visual Studio], Dataset Designer
- Dataset Designer, walkthroughs
- datasets [Visual Basic], creating
ms.assetid: 12360f54-db6c-45d2-a91f-fee43214b555
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 1a9d47431497f05fd5538510b39b44298587dd0e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49287360"
---
# <a name="walkthrough-creating-a-dataset-with-the-dataset-designer"></a>演练：使用数据集设计器创建数据集
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在本演练将创建数据集使用**数据集设计器**。 它将指导您完成创建新的项目并添加新的过程**数据集**到它的项。 您将学习如何创建不使用向导根据数据库中的表的表。  
  
 本演练涉及以下任务：  
  
-   创建一个新**Windows 应用程序**项目。  
  
-   添加一个空**数据集**到项目的项。  
  
-   创建和配置应用程序中的数据源，通过生成具有的数据集**数据集设计器**。  
  
-   创建到 Northwind 数据库中的连接**服务器资源管理器**。  
  
-   基于数据库中的表在数据集中使用 Tableadapter 创建表。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你需要：  
  
-   访问 Northwind 示例数据库（SQL Server 或 Access 版）。 有关详细信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
## <a name="creating-a-new-windows-application-project"></a>创建新的 Windows 应用程序项目  
  
#### <a name="to-create-a-new-windows-application-project"></a>创建新的 Windows 应用程序项目  
  
1.  从**文件**菜单中，创建一个新项目。  
  
2.  选择一种编程语言中的**项目类型**窗格。  
  
3.  单击**Windows 应用程序**中**模板**窗格。  
  
4.  将项目命名`DatasetDesignerWalkthrough`，然后单击**确定**。  
  
     [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 将添加到项目**解决方案资源管理器**和设计器中显示新窗体。  
  
## <a name="adding-a-new-dataset-to-the-application"></a>将新的数据集添加到应用程序  
  
#### <a name="to-add-a-new-dataset-item-to-the-project"></a>若要向项目添加新的数据集项  
  
1.  在 **“项目”** 菜单上，单击 **“添加新项”**。  
  
     “添加新项”对话框随即出现。  
  
2.  在中**模板**的框**添加新项**对话框中，单击**数据集**。  
  
3.  命名数据集`NorthwindDataset`，然后单击**添加**。  
  
     [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 将添加名为的文件**NorthwindDataset.xsd**到项目中将其打开并**数据集设计器**。  
  
## <a name="creating-a-data-connection-in-server-explorer"></a>在服务器资源管理器中创建数据连接  
  
#### <a name="to-create-a-connection-to-the-northwind-database"></a>若要创建到 Northwind 数据库的连接  
  
1.  上**视图**菜单上，单击**服务器资源管理器**。  
  
2.  在中**服务器资源管理器**，单击**连接到数据库**按钮。  
  
3.  创建到 Northwind 示例数据库的连接。  
  
    > [!NOTE]
    >  您可以连接到 SQL Server 或 Access 版本的 Northwind，本演练。  
  
## <a name="creating-the-tables-in-the-dataset"></a>在数据集中创建表  
 本部分将介绍如何将表添加到数据集。  
  
#### <a name="to-create-the-customers-table"></a>创建 Customers 表  
  
1.  展开中创建的数据连接**服务器资源管理器**，然后展开**表**节点。  
  
2.  拖动**客户**表从**服务器资源管理器**拖到**数据集设计器**。  
  
     一个**客户**数据表并**CustomersTableAdapter**添加到数据集。  
  
#### <a name="to-create-the-orders-table"></a>创建 Orders 表  
  
-   拖动**订单**表从**服务器资源管理器**拖到**数据集设计器**。  
  
     **订单**数据表**OrdersTableAdapter**，和数据之间的关系**客户**并**订单**表将添加到数据集。  
  
#### <a name="to-create-the-orderdetails-table"></a>若要创建 OrderDetails 表  
  
-   拖动**订单详细信息**表从**服务器资源管理器**拖到**数据集设计器**。  
  
     **订单详细信息**数据表**顺序 DetailsTableAdapter**，和之间的数据关系**订单**并**订单详细信息**表将添加到数据集。  
  
## <a name="next-steps"></a>后续步骤  
  
### <a name="to-add-functionality-to-your-application"></a>将功能添加到你的应用程序  
  
-   保存的数据集。  
  
-   选择中的项**数据源**窗口并将其拖到窗体上。 有关详细信息，请参阅[绑定 Windows 窗体控件添加到 Visual Studio 中的数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)。  
  
-   向 Tableadapter 添加更多的查询。 有关详细信息，请参阅[如何： 创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)。  
  
-   添加验证逻辑<xref:System.Data.DataTable.ColumnChanging>或<xref:System.Data.DataTable.RowChanging>数据表中数据集的事件。 有关详细信息，请参阅[验证数据集中](../data-tools/validate-data-in-datasets.md)。  
  
## <a name="see-also"></a>请参阅  
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)