---
title: 属性&lt;属性名称&gt;无法删除，因为它参与关联&lt;关联名称&gt;|Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5121d79e6db6bdef1deb0ee04540295b2a109f72
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>属性&lt;属性名称&gt;无法删除，因为它参与关联&lt;关联名称&gt;
所选的属性被设置为**关联属性**错误消息中指示的类之间关联。 如果属性参与了数据类之间的关联，则无法删除。  
  
 设置**关联属性**为数据类，可以成功删除删除的所需的属性的另一个属性。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1.  在 O/R 设计器中选择连接错误消息中指示的数据类的关联连线。  
  
2.  双击该连线以打开**关联编辑器**对话框。  
  
3.  删除从属性**关联属性**。  
  
4.  再次尝试删除该属性。  
  
## <a name="see-also"></a>请参阅
[O-R 设计器消息](../data-tools/o-r-designer-messages.md)  
[Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)