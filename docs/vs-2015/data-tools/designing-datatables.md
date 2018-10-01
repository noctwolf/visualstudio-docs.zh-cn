---
title: 设计数据表 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Microsoft.VSDesigner.DataSource.DesignTable
- Designer_Microsoft.VSDesigner.DataSource.Designer.DataSourceRootDesigner
- vbdata.Microsoft.VSDesigner.DataSource.DesignTable
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- tables [Visual Studio]
- data [Visual Studio], designing DataTables
- DataTable objects
ms.assetid: 17014125-ab28-45ec-8789-01b6fc9a8e6a
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: f952fbcf6da0185e4f9c1bd6a76b7d15d7f772a9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481865"
---
# <a name="designing-datatables"></a>设计数据表
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 提供了用于创建和编辑数据的表设计时工具 (**DataTable**)。 有关的内容概述**DataTable** ，请参阅[DataTables](http://msdn.microsoft.com/library/52ff0e32-3e5a-41de-9a3b-7b04ea52b83e)。  
  
 以下主题说明如何创建数据表，请将它们添加到使用类型化数据集**数据集设计器**，以及创建和编辑数据列 (**DataColumn**)，定义它们。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：创建数据表](../data-tools/how-to-create-data-tables.md)  
 提供的步骤创建一个新<xref:System.Data.DataTable>与**数据集设计器**。  
  
 [如何： 向数据表添加列](http://msdn.microsoft.com/library/8ca21f77-b99a-47a7-a656-7cfd7a1bd9df)  
 提供的步骤创建一个新<xref:System.Data.DataColumn>中的现有<xref:System.Data.DataTable>。  
  
 [演练：在数据集设计器中创建数据表](../data-tools/walkthrough-creating-a-datatable-in-the-dataset-designer.md)  
 提供创建的分步说明<xref:System.Data.DataTable>以及定义<xref:System.Data.DataColumn>构成其结构的 s。  
  
## <a name="reference"></a>参考  
 <xref:System.Data.DataSet>  
 表示数据在内存中的缓存。  
  
 <xref:System.Data.DataTable>  
 表示内存中数据的一个表。  
  
 <xref:System.Data.DataColumn>  
 表示架构中的列<xref:System.Data.DataTable>。  
  
 <xref:System.Data.DataRelation>  
 表示两个 <xref:System.Data.DataTable> 对象之间的父/子关系。  
  
## <a name="related-sections"></a>相关章节  
 [数据表](http://msdn.microsoft.com/library/52ff0e32-3e5a-41de-9a3b-7b04ea52b83e)  
 介绍如何创建和自定义`DataTable`对象。  
  
 [Tableadapter](http://msdn.microsoft.com/library/09416de9-134c-4dc7-8262-6c8d81e3f364)  
 提供指向这些主题介绍如何创建和编辑 Tableadapter 使用设计时工具。  
  
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)  
 提供指向这些主题介绍连接到 Visual Studio 中的数据的不同方式。  
  
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)  
 提供指向这些主题介绍什么是数据集、 如何创建新的数据集，以及如何创建和编辑的各个对象。  
  
 [将数据提取到应用程序中](../data-tools/fetching-data-into-your-application.md)  
 提供指向这些主题说明如何执行查询和存储的过程，并将数据加载到数据集。  
  
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)  
 提供指向这些主题介绍如何通过数据绑定控件在 Windows 窗体上显示数据。  
  
 [在应用程序中编辑数据](../data-tools/editing-data-in-your-application.md)  
 提供指向介绍了如何在数据集中的数据的主题。  
  
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)  
 提供指向这些主题介绍在何处放置代码以验证数据。  
  
 [保存数据](../data-tools/saving-data.md)  
 提供指向介绍如何将更新后的数据发送到数据库的应用程序中的主题。