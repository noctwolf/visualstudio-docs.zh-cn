---
title: 创建和编辑类型化数据集 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Designer_Microsoft.VSDesigner.DataSource.Designer.DataSourceRootDesigner
- vs.data.adddataset
dev_langs:
- VB
- CSharp
- C++
- aspx
- aspx
helpviewer_keywords:
- datasets [Visual Basic], visual designer
- data [Visual Studio], Dataset Designer
- Dataset Designer
ms.assetid: cd0dbe93-be9b-41e4-bc39-e9300678c1f2
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 8c18717cd2a5c7e05b79dbe575d919ef0c8670dd
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49225832"
---
# <a name="creating-and-editing-typed-datasets"></a>创建和编辑类型化数据集
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**数据集设计器**是一套可视化工具，可用于创建和编辑类型化数据集和它们所包含的各个项。  
  
 **数据集设计器**提供类型化数据集所包含的对象的可视表示形式。 创建和修改[Tableadapter](../data-tools/tableadapter-overview.md)， [TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)， <xref:System.Data.DataTable>s， <xref:System.Data.DataColumn>s，以及<xref:System.Data.DataRelation>与**数据集设计器**。  
  
 若要打开**数据集设计器**，双击中的数据集**解决方案资源管理器**，或右键单击的数据集中**数据源**窗口，然后单击**编辑使用设计器的数据集**。 有关详细信息，请参阅[如何： 在数据集设计器中打开数据集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。 添加新<xref:System.Data.DataSet>项具有**添加新项**对话框将打开**数据集设计器**使用空数据集可供编辑。  
  
> [!NOTE]
>  **数据集设计器**可用于扩展数据集的功能。 双击设计图面或右键单击，然后选择**查看代码**创建分部类文件，可以将代码添加到不会更改或删除由设计器的数据集。 扩展 TableAdapter 的功能的信息，请参阅[扩展 TableAdapter 的功能](../data-tools/extend-the-functionality-of-a-tableadapter.md)。  
  
 下表列出了可以使用实现的常见任务**数据集设计器**。  
  
|到|查看|  
|--------|---------|  
|创建 TableAdapter|[创建和配置 Tableadapter](../data-tools/create-and-configure-tableadapters.md)|  
|编辑 TableAdapter|[如何： 编辑 Tableadapter](http://msdn.microsoft.com/library/ca178745-e35a-45f1-a395-23cddfd8f855)|  
|创建 TableAdapter 查询|[如何：创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)|  
|编辑 TableAdapter 查询|[如何：编辑 TableAdapter 查询](../data-tools/how-to-edit-tableadapter-queries.md)|  
|创建 <xref:System.Data.DataTable>|[如何：创建数据表](../data-tools/how-to-create-data-tables.md)|  
|编辑 <xref:System.Data.DataTable>|[设计数据表](../data-tools/designing-datatables.md)|  
|创建 <xref:System.Data.DataColumn>|[如何： 向数据表添加列](http://msdn.microsoft.com/library/8ca21f77-b99a-47a7-a656-7cfd7a1bd9df)|  
|创建两个之间的关系<xref:System.Data.DataTable>s|[如何： 使用数据集设计器创建 Datarelation](http://msdn.microsoft.com/library/a3ab4803-0b50-4b74-9920-ab20bfbf1aa2)|  
|扩展数据集的功能|[如何： 扩展数据集的功能](http://msdn.microsoft.com/library/dfbc21eb-7ea2-4942-addd-49677f5493be)|  
|将验证添加到数据表的<xref:System.Data.DataTable.ColumnChanging>事件|[如何： 在列更改过程中验证数据](http://msdn.microsoft.com/library/a2680600-67b6-4a40-a77e-b5bc638281c5)|  
|将验证添加到数据表的<xref:System.Data.DataTable.RowChanging>事件|[如何： 在行更改过程中验证数据](http://msdn.microsoft.com/library/afc03c77-dfed-4302-9376-929400468ecc)|  
  
## <a name="creating-objects-on-the-design-surface"></a>在设计图面上创建对象  
 添加和编辑组成数据集的单个对象，可创建数据集。 下表提供了不同的对象中的说明**数据集**选项卡上**工具箱**，可以拖动到设计图面上：  
  
|对象|描述|  
|------------|-----------------|  
|TableAdapter|包含一系列数据命令和用于与基础数据库进行通信和填充数据表的数据连接。 有关详细信息，请参阅[TableAdapter 概述](../data-tools/tableadapter-overview.md)并[创建和配置 Tableadapter](../data-tools/create-and-configure-tableadapters.md)。|  
|查询|TableAdapter 查询是执行 SQL 语句和存储的过程的强类型化的方法。 运行 TableAdapter 查询该表中填充数据的数据或执行其他数据库任务。 有关详细信息，请参阅[如何： 创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)。 将查询拖动到表上将查询添加到该表，，而查询拖动到的空白区域**数据集设计器**创建全局查询。 有关详细信息，请参阅[如何： 向 TableAdapter 添加全局查询](../data-tools/how-to-add-global-queries-to-a-tableadapter.md)。|  
|<xref:System.Data.DataTable>|表示一个内存中从数据库中返回的行的集合。|  
|关系 (<xref:System.Data.DataRelation>)|表示两个父-子关系<xref:System.Data.DataTable>s。 有关详细信息，请参阅[DataRelation 对象介绍](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192)并[演练： 创建数据表之间的关系](http://msdn.microsoft.com/library/9b3f1c87-7098-4ed4-a710-cde8f8059f82)。|  
  
> [!NOTE]
>  **数据集设计器**连接到基础数据库仅在一个数据集时才会创建; 在设计器不会自动检测到数据库的后续更改。 若要刷新现有.xsd，请重新运行**配置向导**。 如果表关系已更改，请移除相关表，然后重新添加到 .xsd。  
  
## <a name="linq-to-dataset"></a>LINQ to Dataset  
 [!INCLUDE[linq_dataset](../includes/linq-dataset-md.md)] 使[LINQ （语言集成查询）](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)中的数据通过<xref:System.Data.DataSet>对象。 有关详细信息，请参阅 [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)。  
  
## <a name="see-also"></a>请参阅  
 [演练： 使用数据集设计器创建数据集](../data-tools/walkthrough-creating-a-dataset-with-the-dataset-designer.md)   
 [演练： 创建带有多个查询的 TableAdapter](../data-tools/walkthrough-creating-a-tableadapter-with-multiple-queries.md)   
 [演练： 在数据集设计器中创建数据表](../data-tools/walkthrough-creating-a-datatable-in-the-dataset-designer.md)   
 [演练： 创建数据表之间的关系](http://msdn.microsoft.com/library/9b3f1c87-7098-4ed4-a710-cde8f8059f82)   
 [演练： 在 Windows 窗体上显示数据](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [“数据源”窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)   
 [Visual Studio 中的数据集工具](../data-tools/dataset-tools-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)