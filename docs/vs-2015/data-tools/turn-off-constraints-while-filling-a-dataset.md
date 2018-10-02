---
title: 填充数据集时关闭约束 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DataRow.BeginEdit
- DataRow.EndEdit
- DataRow.CancelEdit
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- updating datasets, constraints
- constraints [Visual Basic], datasets
- datasets [Visual Basic], constraints
- constraints [Visual Basic], suspending during dataset update
ms.assetid: 553f7d0c-2faa-4c17-b226-dd02855bf1dc
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4b14830b7ed4922b4e383ef245c0366c184b606e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477036"
---
# <a name="turn-off-constraints-while-filling-a-dataset"></a>在填充数据集时关闭约束
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[填充数据集时关闭约束](https://docs.microsoft.com/visualstudio/data-tools/turn-off-constraints-while-filling-a-dataset)。  
  
  
如果数据集包含约束 （如外键约束），通过引发顺序对数据集执行的操作相关的错误。 例如，加载子记录之前 loadingrelated 父记录可以违反了约束，将产生错误。 立即加载子记录，该约束检查相关的父记录并引发错误。  
  
 如果没有任何机制来允许约束暂停，在每次尝试将一条记录加载到子表时，将引发错误。 若要在数据集中挂起的所有约束的另一种方法是使用<xref:System.Data.DataRow.BeginEdit%2A>，和<xref:System.Data.DataRow.EndEdit%2A>属性。  
  
> [!NOTE]
>  验证事件 (例如，<xref:System.Data.DataTable.ColumnChanging>和<xref:System.Data.DataTable.RowChanging>) 时关闭约束后，不会引发。  
  
### <a name="to-suspend-update-constraints-programmatically"></a>若要以编程方式挂起更新约束  
  
-   下面的示例演示如何暂时关闭约束检查的数据集：  
  
     [!code-csharp[VbRaddataEditing#10](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#10)]
     [!code-vb[VbRaddataEditing#10](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#10)]  
  
### <a name="to-suspend-update-constraints-using-the-dataset-designer"></a>若要暂停使用数据集设计器更新约束  
  
1.  打开中的数据集[创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)。 有关详细信息，请参阅[如何： 在数据集设计器中打开数据集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
2.  在中**属性**窗口中，将<xref:System.Data.DataSet.EnforceConstraints%2A>属性设置为`false`。  
  
## <a name="see-also"></a>请参阅  
 [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)   
 [数据集中的关系](../data-tools/relationships-in-datasets.md)

