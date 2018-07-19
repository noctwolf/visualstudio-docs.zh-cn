---
title: 在填充数据集时关闭约束
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DataRow.BeginEdit
- DataRow.EndEdit
- DataRow.CancelEdit
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- updating datasets, constraints
- constraints [Visual Basic], datasets
- datasets [Visual Basic], constraints
- constraints [Visual Basic], suspending during dataset update
ms.assetid: 553f7d0c-2faa-4c17-b226-dd02855bf1dc
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d128216f84228c9cd4946f9a38c6c1b7845f92f1
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117233"
---
# <a name="turn-off-constraints-while-filling-a-dataset"></a>在填充数据集时关闭约束

如果数据集包含约束 （如外键约束），它们可以引发顺序对数据集执行的操作相关的错误。 例如，正在加载子记录之前加载相关的父记录可能违反了约束，并导致错误。 立即加载子记录，该约束检查相关的父记录并引发错误。

如果没有任何机制来允许约束暂停，在每次尝试将一条记录加载到子表时，将引发错误。 若要在数据集中挂起的所有约束的另一种方法是使用<xref:System.Data.DataRow.BeginEdit%2A>，和<xref:System.Data.DataRow.EndEdit%2A>属性。

> [!NOTE]
> 验证事件 (例如，<xref:System.Data.DataTable.ColumnChanging>和<xref:System.Data.DataTable.RowChanging>) 时关闭约束后，不会引发。

## <a name="to-suspend-update-constraints-programmatically"></a>若要以编程方式挂起更新约束

-   下面的示例演示如何暂时关闭约束检查的数据集：

     [!code-csharp[VbRaddataEditing#10](../data-tools/codesnippet/CSharp/turn-off-constraints-while-filling-a-dataset_1.cs)]
     [!code-vb[VbRaddataEditing#10](../data-tools/codesnippet/VisualBasic/turn-off-constraints-while-filling-a-dataset_1.vb)]

## <a name="to-suspend-update-constraints-using-the-dataset-designer"></a>若要暂停使用数据集设计器更新约束

1.  打开中的数据集**数据集设计器**。 有关详细信息，请参阅[演练： 创建数据集设计器中的数据集](walkthrough-creating-a-dataset-with-the-dataset-designer.md)。

2.  在中**属性**窗口中，将<xref:System.Data.DataSet.EnforceConstraints%2A>属性设置为`false`。

## <a name="see-also"></a>请参阅

- [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)
- [数据集中的关系](../data-tools/relationships-in-datasets.md)