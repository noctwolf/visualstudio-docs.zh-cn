---
title: 错误： 防火墙无身份验证 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.firewall.noauth
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: dda1acb8-bed7-4bc8-9991-9cdc49c2ac1e
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b76fbea5871bc4662779098f1d83dab537554e1
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51802481"
---
# <a name="error-firewall-no-authentication"></a>错误：防火墙无身份验证
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

远程计算机上的 Internet 连接防火墙未设置为允许远程调试。 为了使用 `No Authentication` 进行远程调试，必须将 msvsmon.exe 添加到例外列表。 可能还需要打开某些 IPSEC 端口。  
  
> [!NOTE]
>  远程调试器可以自动配置 Windows 防火墙。 在使用除 Windows 防火墙之外的防火墙（如第三方软件防火墙或硬件防火墙）时，必须手动将防火墙配置为允许远程调试。 为此，请允许 msvsmon.exe 正在侦听的 TCP/IP 端口的通信。 默认情况下，这些是端口 4018 和 4019，其中 4018 在所有操作系统上使用，而 4019 仅在 Windows x64 上使用以允许调试 x86 进程。  
  
 有关详细信息，请参阅[设置 Up the Remote Tools 在设备上](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)。



