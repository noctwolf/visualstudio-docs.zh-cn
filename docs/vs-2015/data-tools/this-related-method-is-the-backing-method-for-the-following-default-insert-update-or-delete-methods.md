---
title: 此相关方法是下列默认插入、 更新或删除方法的备份方法 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9f487bab485d11446d8e3f920d04c35a64591771
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476777"
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>此相关方法是以下默认插入、更新或删除方法的支持方法
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[此相关方法是下列默认插入、 更新或删除方法的备份方法](https://docs.microsoft.com/visualstudio/data-tools/this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods)。  
  
  
此相关方法是下列默认插入、更新或删除方法的备份方法。 如果删除这些方法，则备份方法也将被删除。 是否要继续?  
  
 所选的 `DataContext` 方法当前用作 O/R 设计器上某实体类的插入、更新或删除方法之一。 如果删除所选方法，则使用此方法的实体类在更新过程中执行插入、更新或删除时将还原为默认的运行时行为。  
  
### <a name="to-delete-the-selected-method-causing-the-entity-class-to-use-runtime-updates"></a>删除所选方法，使实体类使用运行时更新  
  
-   单击 **“是”**。  
  
     所选方法将被删除，并且使用此方法重写更新行为的所有类将还原为使用默认 LINQ to SQL 运行时行为。  
  
### <a name="to-close-the-message-box-leaving-the-selected-method-unchanged"></a>关闭消息框，不对所选方法进行更改  
  
-   单击“否” 。  
  
     消息框关闭，不进行任何更改。  
  
## <a name="see-also"></a>请参阅  
 [DataContext 方法 （O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)   
 [如何： 分配存储的过程以便执行更新、 插入和删除操作 （O/R 设计器）](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)   
 [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)

