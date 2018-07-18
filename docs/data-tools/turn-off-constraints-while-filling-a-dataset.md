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
ms.openlocfilehash: c27cb590b5a8a4b38a143de5e6faba80414f97ba
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31926136"
---
# <a name="turn-off-constraints-while-filling-a-dataset"></a>在填充数据集时关闭约束

如果数据集包含约束 （如外键约束），则它们可以引发顺序对数据集执行的操作相关的错误。 例如，加载子记录之前加载相关的父记录可以违反约束，并会导致错误。 一旦加载子记录时，约束检查相关的父记录，并引发错误。

如果没有任何机制来允许临时约束挂起，在每次尝试加载到子表的记录时，将引发错误。 挂起数据集中的所有约束的另一个方法是使用<xref:System.Data.DataRow.BeginEdit%2A>，和<xref:System.Data.DataRow.EndEdit%2A>属性。

> [!NOTE]
> 验证事件 (例如，<xref:System.Data.DataTable.ColumnChanging>和<xref:System.Data.DataTable.RowChanging>) 约束处于关闭状态时将不会引发。

## <a name="to-suspend-update-constraints-programmatically"></a>若要以编程方式挂起更新约束

-   下面的示例演示如何暂时关闭约束检查的数据集：

     [!code-csharp[VbRaddataEditing#10](../data-tools/codesnippet/CSharp/turn-off-constraints-while-filling-a-dataset_1.cs)]
     [!code-vb[VbRaddataEditing#10](../data-tools/codesnippet/VisualBasic/turn-off-constraints-while-filling-a-dataset_1.vb)]

## <a name="to-suspend-update-constraints-using-the-dataset-designer"></a>若要挂起更新约束使用数据集设计器

1.  打开中的数据集**数据集设计器**。 有关详细信息，请参阅[演练： 创建数据集设计器中的数据集](walkthrough-creating-a-dataset-with-the-dataset-designer.md)。

2.  在**属性**窗口中，设置<xref:System.Data.DataSet.EnforceConstraints%2A>属性`false`。

## <a name="see-also"></a>请参阅

- [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)
- [数据集中的关系](../data-tools/relationships-in-datasets.md)