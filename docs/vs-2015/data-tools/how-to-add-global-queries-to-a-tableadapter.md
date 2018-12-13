---
title: 如何： 向 TableAdapter 添加全局查询 |Microsoft Docs
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
- global functions, datasets
- scalar functions, datasets
- TableAdapters, global queries
- data [Visual Studio], TableAdapters
- datasets [Visual Basic], scalar functions
- TableAdapter Query Configuration Wizard
- datasets [Visual Basic], global functions
- TableAdapter queries
- queries [Visual Studio], TableAdapters
ms.assetid: 4abffd6b-2e9f-4ef3-99b2-6e9ae4ad4679
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: fd185c9a6803a5e66b1fdaac0f040815328ddb82
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49193890"
---
# <a name="how-to-add-global-queries-to-a-tableadapter"></a>如何： 向 TableAdapter 添加全局查询
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

*全局查询*是返回单个 （标量） 值或空值的 SQL 查询。 通常情况下，全局函数执行数据库操作如插入、 更新、 删除和聚合的信息，例如表或特定的顺序中的所有项的总费用中返回的客户计数。  
  
 通过运行添加全局查询**TableAdapter 查询配置向导**内**数据集设计器**。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-global-query-to-a-dataset"></a>若要向数据集添加全局查询  
  
1.  打开中的数据集**数据集设计器**。 有关详细信息，请参阅[如何： 在数据集设计器中打开数据集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
2.  拖动**查询**从**数据集**选项卡**工具箱**拖到空区域中**数据集设计器**。  
  
     [编辑 Tableadapter](../data-tools/editing-tableadapters.md)随即打开。  
  
3.  选择要使用的查询的连接。 您可以从列表中选择一个，或创建新的连接。 如果创建新的连接，必须将其保存到应用程序配置文件的选项。 有关详细信息，请参阅[如何： 保存和编辑连接字符串](~/E:/Repos/visualstudio-docs-pr/docs/data-tools/how-to-save-and-edit-connection-strings.md)。  
  
4.  选择是否要使用的 SQL 语句或存储的过程。  
  
5.  选择要使用的存储的过程或在**选择查询类型**页的向导中，选择的查询，然后单击类型**下一步**。  
  
6.  提供查询，例如，执行所需的任务， `SELECT COUNT(*) AS CustomerCount FROM Customers`。  
  
    > [!NOTE]
    >  直接将查询拖动**数据集设计器**创建一个方法，将仅返回标量 （单个） 值。 查询或您选择的存储的过程可以返回多个值，而由向导创建的方法将仅返回单个值。 例如，查询可能返回返回的数据的第一行的第一列。  
  
7.  完成向导。将查询添加到**数据集设计器**。 有关运行查询的信息，请参阅[如何： 执行 TableAdapter 查询](http://msdn.microsoft.com/library/c7518855-f896-41c1-b3de-1a8116280593)。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置 Tableadapter](../data-tools/create-and-configure-tableadapters.md)   
 [如何： 创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)   
 [创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)   
 [添加新数据源](../data-tools/add-new-data-sources.md)   
 [如何：连接到数据库中的数据](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [如何： 使用 Windows 窗体 BindingNavigator 控件导航数据](http://msdn.microsoft.com/library/0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb)   
 [演练：在 Windows 窗体上显示数据](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)