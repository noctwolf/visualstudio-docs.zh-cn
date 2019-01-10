---
title: 所选连接使用不支持的数据库提供程序
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: cc74cea11e4c173a11f781af4ee78bf047353c53
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53932059"
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>所选连接使用不支持的数据库提供程序

当拖动项适用于 SQL Server 不使用.NET Framework 数据提供程序时，会出现此消息**服务器资源管理器**或**数据库资源管理器**拖动到[视觉对象中的 LINQ to SQL 工具Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)。

**O/R 设计器**支持仅适用于 SQL Server 使用.NET Framework 提供程序的数据连接。 只有指向 Microsoft SQL Server 或 Microsoft SQL Server 数据库文件的连接才有效。

若要更正此错误，仅通过将项目添加使用用于 SQL Server.NET Framework 数据提供程序的数据连接**O/R 设计器**。

## <a name="see-also"></a>请参阅

- <xref:System.Data.SqlClient>
- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
