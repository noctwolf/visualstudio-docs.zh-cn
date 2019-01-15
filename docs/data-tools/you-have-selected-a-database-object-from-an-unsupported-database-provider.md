---
title: 您从不支持的数据库提供程序选择了数据库对象
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 4efaf92c9f4688d6870c1152be27eb4c8f4ed933
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53894436"
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>您从不支持的数据库提供程序选择了数据库对象

**O/R 设计器**适用于 SQL Server 支持仅.NET Framework 数据提供程序 (<xref:System.Data.SqlClient>)。 虽然可以单击“确定”并继续使用来自不支持的数据库提供程序的对象，但在运行时可能遇到意外行为。

> [!NOTE]
> 仅支持使用用于 SQL Server 的 .NET Framework 数据提供程序的数据连接。

## <a name="to-correct-this-error"></a>更正此错误

- 单击 **“确定”**。

   你可以继续设计映射到使用不支持的数据库提供程序的连接的实体类。 使用不支持的数据库提供程序时，可能遇到意外行为。

    或

- 单击“取消”。

   操作停止。 创建或使用采用了用于 SQL Server 的 .NET Framework 提供程序的数据连接。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)