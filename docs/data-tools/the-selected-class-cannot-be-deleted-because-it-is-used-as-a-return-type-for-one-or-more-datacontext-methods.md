---
title: 无法删除所选类，因为该类用作一个或多个 DataContext 方法的返回类型
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c1460f8e3484633643d5b7bc9c7df181989b83ff
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>无法删除所选类，因为该类用作一个或多个 DataContext 方法的返回类型

一个或多个 <xref:System.Data.Linq.DataContext> 方法的返回类型是所选实体类。 删除用作 <xref:System.Data.Linq.DataContext> 方法返回类型的实体类将导致项目编译失败。 若要删除选定的实体类，请找出使用该类的 <xref:System.Data.Linq.DataContext> 方法并将这些方法的返回类型设置为其他实体类。

若要还原的返回类型<xref:System.Data.Linq.DataContext>方法为原始自动生成类型，首先删除<xref:System.Data.Linq.DataContext>从方法窗格中的方法，然后将从对象**服务器资源管理器**/ **数据库资源管理器**拖动到 O/R 设计器试。

## <a name="to-correct-this-error"></a>更正此错误

1. 标识<xref:System.Data.Linq.DataContext>通过选择用作返回类型的实体类的方法<xref:System.Data.Linq.DataContext>方法中的方法窗格中，并检查**返回类型**中的属性**属性**窗口.

2. 设置**返回类型**为不同的实体类或删除<xref:System.Data.Linq.DataContext>从方法窗格中的方法。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)