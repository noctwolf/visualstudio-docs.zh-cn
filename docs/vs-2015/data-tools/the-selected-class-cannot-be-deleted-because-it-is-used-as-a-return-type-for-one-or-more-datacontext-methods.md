---
title: 无法删除所选的类，因为它针对一个或多个 DataContext 方法的返回类型用 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d8eb5f93ef3770b0d275d71d818e44d52a067f83
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60094679"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>无法删除所选类，因为该类用作一个或多个 DataContext 方法的返回类型
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

一个或多个 <xref:System.Data.Linq.DataContext> 方法的返回类型是所选实体类。 删除用作 <xref:System.Data.Linq.DataContext> 方法返回类型的实体类将导致项目编译失败。 若要删除选定的实体类，请找出使用该类的 <xref:System.Data.Linq.DataContext> 方法并将这些方法的返回类型设置为其他实体类。  
  
 若要还原的返回类型<xref:System.Data.Linq.DataContext>方法添加到其原始的自动生成类型，请先删除<xref:System.Data.Linq.DataContext>方法从方法窗格，然后将从对象**服务器资源管理器**/ **数据库资源管理器**拖动到 O/R 设计器再次。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1. 识别<xref:System.Data.Linq.DataContext>通过选择用作返回类型的实体类的方法<xref:System.Data.Linq.DataContext>方法中的方法窗格并检查**返回类型**中的属性**属性**窗口.  
  
2. 将“返回类型”设置为其他实体类，或从方法窗格中删除该 <xref:System.Data.Linq.DataContext> 方法。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [演练：创建 LINQ to SQL 类 （O-R 设计器）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [DataContext 方法 （O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)   
 [如何：更改 DataContext 方法的返回类型（O/R 设计器）](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)
