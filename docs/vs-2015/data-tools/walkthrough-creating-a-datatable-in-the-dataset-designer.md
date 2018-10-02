---
title: 演练： 创建数据表中数据集设计器 |Microsoft Docs
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
- DataTable objects, creating
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
- data [Visual Studio], Dataset Designer
ms.assetid: abf0a2b5-e4e5-422e-97ef-55a0e35a82df
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 832dba200fca438d000bae101381389ea20cfb17
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472057"
---
# <a name="walkthrough-creating-a-datatable-in-the-dataset-designer"></a>演练：在数据集设计器中创建数据表
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本演练说明了如何创建<xref:System.Data.DataTable>（不带 TableAdapter) 使用**数据集设计器**。 有关创建包含 Tableadapter 的数据表的信息，请参阅[创建和配置 Tableadapter](../data-tools/create-and-configure-tableadapters.md)。  
  
 本演练涉及以下任务：  
  
-   创建一个新的 Windows 应用程序项目  
  
-   将新的数据集添加到应用程序  
  
-   将新的数据表添加到数据集  
  
-   向数据表添加列  
  
-   设置表的主键  
  
## <a name="creating-a-new-windows-application"></a>创建新的 Windows 应用程序  
  
#### <a name="to-create-a-new-windows-application-project"></a>创建新的 Windows 应用程序项目  
  
1.  从**文件**菜单中，创建一个新项目。  
  
2.  选择一种编程语言中的**项目类型**窗格。  
  
3.  单击**Windows 应用程序**中**模板**窗格。  
  
4.  将项目命名`DataTableWalkthrough`，然后单击**确定**。  
  
     Visual Studio 将添加到项目**解决方案资源管理器**，并显示**Form1**在设计器中。  
  
## <a name="adding-a-new-dataset-to-the-application"></a>将新的数据集添加到应用程序  
  
#### <a name="to-add-a-new-dataset-item-to-the-project"></a>若要向项目添加新的数据集项  
  
1.  在 **“项目”** 菜单上，单击 **“添加新项”**。  
  
     添加新项对话框中显示。  
  
2.  在中**模板**框中，选择**数据集**。  
  
3.  单击 **添加**。  
  
     Visual Studio 将添加名为的文件**DataSet1.xsd**到项目中将其打开并**数据集设计器**。  
  
## <a name="adding-a-new-datatable-to-the-dataset"></a>将一个新的 DataTable 添加到数据集  
  
#### <a name="to-add-a-new-data-table-to-the-dataset"></a>若要将新的数据表添加到数据集  
  
1.  拖动**DataTable**从**数据集**选项卡**工具箱**拖到**数据集设计器**。  
  
     名为的表**DataTable1**添加到数据集。  
  
    > [!NOTE]
    >  若要创建包含 TableAdapter 的数据表，请参阅[演练： 创建带有多个查询的 TableAdapter](../data-tools/walkthrough-creating-a-tableadapter-with-multiple-queries.md)。  
  
2.  单击的标题栏**DataTable1**并将其重命名`Music`。  
  
## <a name="adding-columns-to-the-data-table"></a>向数据表添加列  
  
#### <a name="to-add-columns-to-the-data-table"></a>若要向数据表添加列  
  
1.  右键单击**音乐**表。 指向**外**，然后单击**列**。  
  
2.  名称列`SongID`。  
  
3.  在中**属性**窗口中，将<xref:System.Data.DataColumn.DataType%2A>属性设置为<xref:System.Int16?displayProperty=fullName>。  
  
4.  重复此过程，并添加以下列：  
  
     `SongTitle`: <xref:System.String?displayProperty=fullName>  
  
     `Artist`: <xref:System.String?displayProperty=fullName>  
  
     `Genre`: <xref:System.String?displayProperty=fullName>  
  
## <a name="setting-the-primary-key-for-the-table"></a>设置表的主键  
 数据的所有表应都具有主键。 主键唯一标识数据表中的特定记录。  
  
#### <a name="to-set-the-primary-key-of-the-data-table"></a>若要设置数据的表的主键  
  
-   右键单击**SongID**列中，并单击**设置主键**。  
  
     旁边会显示密钥图标**SongID**列。  
  
## <a name="saving-your-project"></a>正在保存你的项目  
  
#### <a name="to-save-the-datatablewalkthrough-project"></a>若要保存 DataTableWalkthrough 项目  
  
-   上**文件**菜单上，单击**全部保存**。  
  
## <a name="next-steps"></a>后续步骤  
 现在，已创建表，您可能想要执行以下操作之一：  
  
|到|查看|  
|--------|---------|  
|创建将数据输入窗体|[演练： 在 Windows 窗体上显示数据](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)。|  
|将数据添加到表|[将数据添加到 DataTable](http://msdn.microsoft.com/library/d6aa8474-7bde-48f7-949d-20dc38a1625b)。|  
|表中的视图数据|[查看数据表中的数据](http://msdn.microsoft.com/library/1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc)。|  
|编辑数据|[数据表编辑](http://msdn.microsoft.com/library/f08008a9-042e-4de9-94f3-4f0e502b1eb5)|  
|从表中删除行|[DataRow 删除](http://msdn.microsoft.com/library/c34f531d-4b9b-4071-b2d7-342c402aa586)|  
  
## <a name="see-also"></a>请参阅  
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)   
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)