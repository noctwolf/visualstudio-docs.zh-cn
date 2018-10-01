---
title: 如何： 创建数据表 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Microsoft.VSDesigner.DataSource.DesignTable
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], creating data tables
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
ms.assetid: 0e8bf4c4-3d05-4b20-9926-9d29914b26ed
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 596c2760e100bc45eefdde10743b3d9b45490b91
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481232"
---
# <a name="how-to-create-data-tables"></a>如何：创建数据表
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

数据可以存储在内存中<xref:System.Data.DataTable>对象。 (数据集组成的<xref:System.Data.DataTable>对象。)通常使用 Tableadapter 使用创建新数据表[TableAdapter 配置向导](http://msdn.microsoft.com/library/3a373dd9-7b34-4d3c-a48b-69414512bac8)或通过将数据库对象从拖**服务器资源管理器**拖动到**数据集设计器**.  
  
 创建新的 Tableadapter 中时，数据的表进行创建作为副产品[数据源配置向导](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)，但也可以单独创建。 通过拖动创建单独的数据表<xref:System.Data.DataTable>对象从**数据集**选项卡**工具箱**拖动到**数据集设计器**。  
  
> [!NOTE]
>  若要以编程方式创建数据的表，请参阅[创建数据表](http://msdn.microsoft.com/library/eecf9d78-60e3-4fdc-8de0-e56c13a89414)。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datatable-with-tableadapter"></a>使用 TableAdapter 创建数据表  
 使用 Tableadapter 的数据表包括用数据填充表，并将更改写回数据库的方法。 通过运行创建 Tableadapter **TableAdapter 配置向导**或通过将数据库对象从拖**服务器资源管理器**拖到**数据集设计器**。  
  
#### <a name="to-create-a-new-data-table-with-tableadapter"></a>若要使用 TableAdapter 创建新的数据表  
  
1.  打开中的数据集**数据集设计器**。 有关信息，请参阅[如何： 在数据集设计器中打开数据集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
2.  拖动**TableAdapter**从**数据集**选项卡**工具箱**拖到**数据集设计器**。  
  
     **TableAdapter 配置向导**随即打开。  
  
3.  完成向导。 有关详细信息，请参阅[TableAdapter 配置向导](http://msdn.microsoft.com/library/3a373dd9-7b34-4d3c-a48b-69414512bac8)  
  
#### <a name="to-create-a-new-data-table-with-a-tableadapter-from-server-explorer"></a>若要使用 TableAdapter 从服务器资源管理器创建新的数据表  
  
1.  打开中的数据集**数据源设计器**。  
  
2.  将数据库对象 （例如，表） 从**服务器资源管理器**拖动到**数据集设计器**。  
  
## <a name="creating-a-standalone-datatable"></a>创建独立数据表  
 单独的表需要具有`Fill`逻辑实现以填充数据。 有关填充独立数据的表的信息，请参阅[填充数据集从 DataAdapter](http://msdn.microsoft.com/library/3fa0ac7d-e266-4954-bfac-3fbe2f913153)。  
  
#### <a name="to-create-a-new-stand-alone-data-table"></a>若要创建新的独立数据表  
  
1.  打开中的数据集**数据集设计器**。  
  
2.  拖动<xref:System.Data.DataTable>从**数据集**选项卡**工具箱**拖动到**数据集设计器**。  
  
3.  添加列来定义您的数据的表。 有关详细信息，请参阅[如何： 向数据表添加列](http://msdn.microsoft.com/library/8ca21f77-b99a-47a7-a656-7cfd7a1bd9df)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.DataTable>   
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [演练： 在 Windows 窗体上显示数据](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)   
 [创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)   
 [添加新数据源](../data-tools/add-new-data-sources.md)   
 [“数据源”窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)   
 [如何：连接到数据库中的数据](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)