---
title: 如何： 提交数据集中的更改 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DataSet.AcceptChanges
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- datasets [Visual Basic], committing changes
ms.assetid: 51931353-4d22-4e35-a9ef-6f2b44e1f7d9
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 41d27c248763f42db6543db0a9b4e56e4c4eac82
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49276427"
---
# <a name="how-to-commit-changes-in-a-dataset"></a>如何：提交数据集中的更改
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

通过更新、 插入和删除记录，可以对在数据集中的记录进行更改，如数据集维护原始版本和当前版本记录。 另外，每个行<xref:System.Data.DataRow.RowState%2A>是否记录处于其原始状态或具有已更新、 插入或删除跟踪的属性。 当您需要查找特定行的版本时，此信息很有用。 通常情况下，将获取所有已更改的记录将发送到另一个进程的子集。 有关详细信息，请参阅[如何： 检索已更改行](http://msdn.microsoft.com/library/6ff0cbd0-5253-48e7-888a-144d56c2e0a9)。 在处理所有已更改的行后，可以通过调用提交所做的更改`AcceptChanges`方法<xref:System.Data.DataSet>， <xref:System.Data.DataTable>，或<xref:System.Data.DataRow>。 `AcceptChanges`时调用的 update 方法将自动调用方法[TableAdapter](../data-tools/tableadapter-overview.md)或数据适配器。 调用`AcceptChanges`后将更改提交到数据库。  
  
 当您调用<xref:System.Data.DataSet.AcceptChanges%2A>上<xref:System.Data.DataSet>，则所有<xref:System.Data.DataRow>仍处于编辑模式的对象已成功结束其编辑。 <xref:System.Data.DataRow.RowState%2A>每个属性<xref:System.Data.DataRow>也会更改;<xref:System.Data.DataRowState>并<xref:System.Data.DataRowState>行变得<xref:System.Data.DataRowState>，和<xref:System.Data.DataRowState>删除行。  
  
 如果<xref:System.Data.DataSet>包含<xref:System.Data.ForeignKeyConstraint>对象，则调用<xref:System.Data.DataSet.AcceptChanges%2A>方法还会导致<xref:System.Data.AcceptRejectRule>强制执行。  
  
### <a name="to-commit-changes-in-a-dataset"></a>若要提交数据集中的更改  
  
-   调用`AcceptChanges`上的方法<xref:System.Data.DataSet>， <xref:System.Data.DataTable>，或<xref:System.Data.DataRow>来提交这些对象中的更改。  
  
     下面的示例演示如何调用`AcceptChanges`方法来提交中的更改`Customers`后更新数据源的表：  
  
     [!code-csharp[VbRaddataEditing#11](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#11)]
     [!code-vb[VbRaddataEditing#11](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#11)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.DataSet.AcceptChanges%2A?displayProperty=fullName>   
 <xref:System.Data.DataTable.AcceptChanges%2A?displayProperty=fullName>   
 <xref:System.Data.DataRow.AcceptChanges%2A?displayProperty=fullName>   
 [保存数据](../data-tools/saving-data.md)   
 [如何： 检索已更改的行](http://msdn.microsoft.com/library/6ff0cbd0-5253-48e7-888a-144d56c2e0a9)