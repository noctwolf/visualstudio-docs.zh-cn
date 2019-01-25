---
title: 错误：SQL 找不到 Ssdebugps | Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d0c10c2ba2a5b9da700d698d553cdf49a7a0a136
ms.sourcegitcommit: 73861cd0ea92e50a3be1ad2a0ff0a7b07b057a1c
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54153662"
---
# <a name="error-sql-can39t-find-ssdebugps"></a>错误：SQL 找不到 Ssdebugps

SSDEBUGPS.dll 为 SQL Server Debugging Host 组件。

此错误在尝试开始调试时发生，指示指定的文件在 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 计算机上不存在。 可能的原因是从未运行远程调试安装，或是由于某种原因删除了此文件。

有两种方法可以纠正此错误：重新运行远程调试安装，以及将该文件复制到 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 计算机上。

若要重新运行远程调试安装，请按照的说明[远程调试](../debugger/remote-debugging.md)。

如果可以找到 ssdebugps.dll 的某个副本，则可以将其复制到 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 计算机上。 如果存在，该文件会位于目录 \Program Files\ Common Files\Microsoft Shared\SQL Debugging 中。 你可能会发现它在另一台[!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)]计算机，或已安装 Visual Studio 2005 的计算机上。

将 SSDEBUGPS.dll 复制到 SQL Server 2005 计算机上：

1. 将该文件复制到 [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] 计算机上具有相同名称和路径的目录中。

2. 通过打开“命令提示符”并运行下面的命令来注册该文件：

    ```cmd
    regsvr32 ssdebugps.dll
    ```
