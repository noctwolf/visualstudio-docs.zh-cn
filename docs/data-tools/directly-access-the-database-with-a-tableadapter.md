---
title: 使用 TableAdapter 直接访问数据库
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: c6185103daab7d030787bd6f4f4f125b0fb8bcdb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54997151"
---
# <a name="directly-access-the-database-with-a-tableadapter"></a>使用 TableAdapter 直接访问数据库

除了`InsertCommand`， `UpdateCommand`，和`DeleteCommand`，可以直接对数据库运行的方法创建 Tableadapter。 您可以调用这些方法 (`TableAdapter.Insert`， `TableAdapter.Update`，和`TableAdapter.Delete`) 来操作直接在数据库中的数据。

如果不想要创建以下直接方法，设置 TableAdapter`GenerateDbDirectMethods`属性设置为`false`中**属性**窗口。 如果将任何查询添加到 TableAdapter 的主查询除了 TableAdapter，它们是独立的查询，不生成这些`DbDirect`方法。

## <a name="send-commands-directly-to-a-database"></a>直接向数据库发送命令

调用 TableAdapter`DbDirect`你尝试完成执行的任务的方法。

### <a name="to-insert-new-records-directly-into-a-database"></a>若要直接向数据库中插入新记录

-   调用 TableAdapter 的`Insert`方法，在值中的每个列将作为参数传递。 以下过程使用`Region`作为示例 Northwind 数据库中的表。

    > [!NOTE]
    > 如果没有可用的实例，实例化想要使用的 TableAdapter。

     [!code-vb[VbRaddataSaving#15](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_1.vb)]
     [!code-csharp[VbRaddataSaving#15](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_1.cs)]

### <a name="to-update-records-directly-in-a-database"></a>若要直接在数据库中更新记录

-   调用 TableAdapter 的`Update`方法，在新的和原始值中的每个列将作为参数传递。

    > [!NOTE]
    > 如果没有可用的实例，实例化想要使用的 TableAdapter。

     [!code-vb[VbRaddataSaving#18](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_2.vb)]
     [!code-csharp[VbRaddataSaving#18](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_2.cs)]

### <a name="to-delete-records-directly-from-a-database"></a>若要直接从数据库中删除记录

-   调用 TableAdapter`Delete`方法，在值中的每个列将作为参数传递的`Delete`方法。 以下过程使用`Region`作为示例 Northwind 数据库中的表。

    > [!NOTE]
    > 如果没有可用的实例，实例化想要使用的 TableAdapter。

     [!code-vb[VbRaddataSaving#21](../data-tools/codesnippet/VisualBasic/directly-access-the-database-with-a-tableadapter_3.vb)]
     [!code-csharp[VbRaddataSaving#21](../data-tools/codesnippet/CSharp/directly-access-the-database-with-a-tableadapter_3.cs)]

## <a name="see-also"></a>请参阅

- [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)