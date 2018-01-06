---
title: "错误： 防火墙无身份验证 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.firewall.noauth
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: aed8e53436b43ba6d5cef6b50691df278f639f6a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="error-firewall-no-authentication"></a>错误：防火墙无身份验证
远程计算机上的 Internet 连接防火墙未设置为允许远程调试。 为了使用 `No Authentication` 进行远程调试，必须将 msvsmon.exe 添加到例外列表。 可能还需要打开某些 IPSEC 端口。  
  
> [!NOTE]
>  远程调试器可以自动配置 Windows 防火墙。 在使用除 Windows 防火墙之外的防火墙（如第三方软件防火墙或硬件防火墙）时，必须手动将防火墙配置为允许远程调试。 为此，请允许 msvsmon.exe 正在侦听的 TCP/IP 端口的通信。 默认情况下，这些是端口 4018 和 4019，其中 4018 在所有操作系统上使用，而 4019 仅在 Windows x64 上使用以允许调试 x86 进程。  
  
 有关详细信息，请参阅[远程调试](../debugger/remote-debugging.md)。