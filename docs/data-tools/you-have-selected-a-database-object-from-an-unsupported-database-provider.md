---
title: 您从不支持的数据库提供程序选择了数据库对象
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0646f153149d887ce87f2688d9c28b3da502ba1c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>您从不支持的数据库提供程序选择了数据库对象

O/R 设计器支持用于 SQL Server 仅.NET Framework 数据提供程序 (<xref:System.Data.SqlClient>)。 尽管你可以单击**确定**并继续使用来自不受支持的数据库提供程序的对象，你可能会在运行时遇到意外的行为。

> [!NOTE]
> 仅支持使用用于 SQL Server 的 .NET Framework 数据提供程序的数据连接。

## <a name="to-correct-this-error"></a>更正此错误

- 单击 **“确定”**。

   你可以继续设计映射到使用不支持的数据库提供程序的连接的实体类。 使用不支持的数据库提供程序时，可能遇到意外行为。

    -或-

- 单击**取消**。

   操作停止。 创建或使用采用了用于 SQL Server 的 .NET Framework 提供程序的数据连接。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)