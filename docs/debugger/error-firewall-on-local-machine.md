---
title: 错误：本地计算机上的防火墙 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.firewall.localmachine
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d2fafd14a816f75ac4acdf4de7db0ceda1430652
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53919834"
---
# <a name="error-firewall-on-local-machine"></a>错误：本地计算机上的防火墙
本地计算机（运行 Visual Studio 的计算机）上的 Internet 连接防火墙未设置为允许远程调试。 为了使用默认传输进行托管或本机远程调试，必须为 DCOM 通信打开 TCP 135 端口。 必须打开文件和打印机共享，且必须将 devenv.exe 添加到例外列表。 可能还需要打开某些 IPSEC 端口。  
  
 有关详细信息，请参阅[远程调试](../debugger/remote-debugging.md)。