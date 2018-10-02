---
title: 无法删除所选的类，因为它针对一个或多个 DataContext 方法的返回类型用 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9a285922a004669b75d33ac6d866e1f21f5d6442
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481488"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>无法删除所选类，因为该类用作一个或多个 DataContext 方法的返回类型
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[无法删除所选的类，因为它针对一个或多个 DataContext 方法的返回类型用](https://docs.microsoft.com/visualstudio/data-tools/the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods)。  
  
  
一个或多个 <xref:System.Data.Linq.DataContext> 方法的返回类型是所选实体类。 删除用作 <xref:System.Data.Linq.DataContext> 方法返回类型的实体类将导致项目编译失败。 若要删除选定的实体类，请找出使用该类的 <xref:System.Data.Linq.DataContext> 方法并将这些方法的返回类型设置为其他实体类。  
  
 若要还原的返回类型<xref:System.Data.Linq.DataContext>方法添加到其原始的自动生成类型，请先删除<xref:System.Data.Linq.DataContext>方法从方法窗格，然后将从对象**服务器资源管理器**/ **数据库资源管理器**拖动到 O/R 设计器再次。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1.  识别<xref:System.Data.Linq.DataContext>通过选择用作返回类型的实体类的方法<xref:System.Data.Linq.DataContext>方法中的方法窗格并检查**返回类型**中的属性**属性**窗口.  
  
2.  设置**返回类型**到不同的实体类或删除<xref:System.Data.Linq.DataContext>方法从方法窗格。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [演练： 创建 LINQ to SQL 类 （O-R 设计器）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [DataContext 方法 （O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)   
 [如何：更改 DataContext 方法的返回类型（O/R 设计器）](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)

