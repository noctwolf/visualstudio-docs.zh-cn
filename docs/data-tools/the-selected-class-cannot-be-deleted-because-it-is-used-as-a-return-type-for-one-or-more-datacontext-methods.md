---
title: 无法删除所选类，因为该类用作一个或多个 DataContext 方法的返回类型
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 21ef0f86d701c899328044a03cde8035a1e7292d
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174193"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>无法删除所选类，因为该类用作一个或多个 DataContext 方法的返回类型

一个或多个 <xref:System.Data.Linq.DataContext> 方法的返回类型是所选实体类。 删除用作返回类型的实体类<xref:System.Data.Linq.DataContext>方法将导致项目无法编译。 若要删除选定的实体类，请找出使用该类的 <xref:System.Data.Linq.DataContext> 方法并将这些方法的返回类型设置为其他实体类。

若要还原的返回类型<xref:System.Data.Linq.DataContext>方法添加到其原始的自动生成类型，请先删除<xref:System.Data.Linq.DataContext>方法从**方法**窗格，然后将从对象**服务器资源管理器** /**数据库资源管理器**拖动到**O/R 设计器**试。

## <a name="to-correct-this-error"></a>更正此错误

1. 识别<xref:System.Data.Linq.DataContext>通过选择用作返回类型的实体类的方法<xref:System.Data.Linq.DataContext>中的方法**方法**窗格和检查**返回类型**中属性**属性**窗口。

2. 设置**返回类型**到不同的实体类或删除<xref:System.Data.Linq.DataContext>方法从方法窗格。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)