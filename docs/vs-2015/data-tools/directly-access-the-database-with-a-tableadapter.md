---
title: 直接访问使用 TableAdapter 数据库 |Microsoft Docs
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
- databases [Visual Basic], accessing with a TableAdapter
- DBDirect methods
- datasets [Visual Basic], adding to projects
- data [Visual Studio], saving
- TableAdapter.Delete method
- GenerateDbDirectMethods property
- TableAdapter.Insert method
- TableAdapter.GenerateDBDirectMethods property
- TableAdapter.Update method
- saving data
- TableAdapters
ms.assetid: 012c5924-91f7-4790-b2a6-f51402b7014b
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 689bc12129df82fb57bd0247ffa7f1e896aa4c92
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478089"
---
# <a name="directly-access-the-database-with-a-tableadapter"></a>使用 TableAdapter 直接访问数据库
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[直接访问使用 TableAdapter 数据库](https://docs.microsoft.com/visualstudio/data-tools/directly-access-the-database-with-a-tableadapter)。  
  
  
除了`InsertCommand`， `UpdateCommand`，和`DeleteCommand`，可以直接对数据库运行的方法创建 Tableadapter。 这些方法 (`TableAdapter.Insert`， `TableAdapter.Update`，和`TableAdapter.Delete`) 可以调用以操作直接在数据库中的数据。  
  
 如果不想要创建以下直接方法，设置 TableAdapter`GenerateDbDirectMethods`属性设置为`false`中**属性**窗口。 如果将任何查询添加到 TableAdapter 的主查询除了 TableAdapter，它们不生成这些 DbDirect 方法的独立查询。  
  
## <a name="sendcommandsdirectly-to-a-database"></a>Sendcommandsdirectly 到数据库  
 调用 TableAdapter DbDirect 方法用于执行你尝试完成的任务。  
  
#### <a name="to-insert-new-records-directly-into-a-database"></a>若要直接向数据库中插入新记录  
  
-   调用 TableAdapter 的`Insert`方法，在值中的每个列将作为参数传递。 以下过程使用`Region`表中 Northwind databaseas 示例。  
  
    > [!NOTE]
    >  如果没有可用的实例，实例化想要使用的 TableAdapter。  
  
     [!code-csharp[VbRaddataSaving#15](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#15)]
     [!code-vb[VbRaddataSaving#15](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#15)]  
  
#### <a name="to-update-records-directly-in-a-database"></a>若要直接在数据库中更新记录  
  
-   调用 TableAdapter 的`Update`方法，在新的和原始值中的每个列将作为参数传递。  
  
    > [!NOTE]
    >  如果没有可用的实例，实例化想要使用的 TableAdapter。  
  
     [!code-csharp[VbRaddataSaving#18](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#18)]
     [!code-vb[VbRaddataSaving#18](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#18)]  
  
#### <a name="to-delete-records-directly-from-a-database"></a>若要直接从数据库中删除记录  
  
-   调用 TableAdapter`Delete`方法，在值中的每个列将作为参数传递的`Delete`方法。 以下过程使用`Region`表中 Northwind databaseas 示例。  
  
    > [!NOTE]
    >  如果没有可用的实例，实例化想要使用的 TableAdapter。  
  
     [!code-csharp[VbRaddataSaving#21](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#21)]
     [!code-vb[VbRaddataSaving#21](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>请参阅  
 [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)

