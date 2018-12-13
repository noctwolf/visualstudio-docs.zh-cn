---
title: 该属性&lt;属性名称&gt;不能删除，因为它参与了关联&lt;关联名称&gt;|Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cdd2c2ab26709a017801e8ae34e4ee6f2223c2c3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49177731"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>该属性&lt;属性名称&gt;不能删除，因为它参与了关联&lt;关联名称&gt;
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
所选的属性设置为**关联属性**错误消息中指示的类之间的关联。 如果属性参与了数据类之间的关联，则无法删除。  
  
 设置**关联属性**到不同的数据类可以成功删除删除所需的属性的属性。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1.  在 O/R 设计器中选择连接错误消息中指示的数据类的关联连线。  
  
2.  双击该连线以打开**关联编辑器**对话框。  
  
3.  删除属性**关联属性**。  
  
4.  再次尝试删除该属性。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [如何： 创建 LINQ to SQL 类 （O/R 设计器） 之间的关联 （关系）](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)   
 [演练： 创建 LINQ to SQL 类 （O-R 设计器）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)

