---
title: 错误：TRANSACT-SQL 执行未经调试便已结束 |Microsoft Docs
ms.date: 11/08/2018
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.sqlde_sql_executed_but_not_debugged
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 71d1f14bef8eb69fa6c6fc4d9c3f669826079c99
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850161"
---
# <a name="error-transact-sql-execution-ended-without-debugging"></a>错误：Transact-SQL 执行未经调试便已结束

在你尝试调试 Transact-SQL 或 SQLCLR 过程，而调试器未收到来自 SQL Server 的调试消息时，就会出现此错误。

此问题可能是由于网络问题或 SQL 服务器上的问题，但最可能的原因是权限问题。

这涉及到两种帐户：

- 应用程序帐户是 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 运行时所用的用户帐户。

- 连接帐户是用于建立到 SQL Server 的连接的标识。 此帐户并不一定像的连接使用 SQL 身份验证运行 Visual Studio 的标识相同。

  SQL 调试要求应用程序帐户必须与连接帐户匹配或者是 sysadmin。

  如果使用的类似于 sa 的 SQL 帐户名称，应用程序帐户必须是设置在 SQL Server 上为系统管理员。 默认情况下，SQL server 运行的计算机上的管理员是 SQL Server 系统管理员。

  若要纠正此错误，可能需要：

  - 验证权限设置。 有关详细信息，请参阅[如何：设置 SQL Server 权限以进行调试](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)。

  - 如果设置正确，请确保 SQL 调试也正确。

  - 请咨询网络或数据库管理员。

## <a name="see-also"></a>请参阅

- [设置 SQL 调试](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/s4sszxst(v=vs.100))
- [如何：设置 SQL Server 权限以进行调试](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)
- [调试器设置和准备](../debugger/debugger-settings-and-preparation.md)
- [远程调试](../debugger/remote-debugging.md)