---
title: 所选连接使用不支持的数据库提供程序
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 2f4d2ce764f4824fdcff897c1dab542a53f80e0f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>所选连接使用不支持的数据库提供程序

当拖动项适用于 SQL Server 不使用.NET Framework 数据提供程序时，会出现此消息**服务器资源管理器**/**数据库资源管理器**到[LINQ to SQLVisual Studio 中的工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)。

[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]仅支持使用用于 SQL Server 的 .NET Framework 提供程序的数据连接。 只有指向 Microsoft SQL Server 或 Microsoft SQL Server 数据库文件的连接才有效。

若要更正此错误，仅通过将项目添加用于 SQL Server 的.NET Framework 数据提供程序的数据连接[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]。

## <a name="see-also"></a>请参阅

- <xref:System.Data.SqlClient>
- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
