---
title: 一个或多个所选项包含设计器不支持的数据类型
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 71dcd4f9-2946-42c5-9ce4-99c819ea2785
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 68d8675df54e37b9a6122b853e742addc0d8060c
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089485"
---
# <a name="one-or-more-selected-items-contain-a-data-type-that-is-not-supported-by-the-designer"></a>一个或多个所选项包含设计器不支持的数据类型

从一个或多个项拖动**服务器资源管理器**或**数据库资源管理器**拖到**O/R 设计器**包含不支持的数据类型**O/R 设计器**，例如[CLR 用户定义类型](/dotnet/framework/data/adonet/sql/clr-user-defined-types)。

## <a name="to-correct-this-error"></a>更正此错误

1. 创建一个基于所需的表的视图，且其中不包括不支持的数据类型。

2. 将从该视图**服务器资源管理器**或**数据库资源管理器**拖到设计器。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)