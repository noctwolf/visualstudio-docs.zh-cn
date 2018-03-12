---
title: "错误： RPC 要求身份验证 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.rpc_requires_authentication
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 73cd474d415a49b6dd9075559d8618289b1b0d21
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="error-rpc-requires-authentication"></a>错误：RPC 要求身份验证
Visual Studio 调试器无法连接到远程计算机。 本地计算机上启用了阻止远程调试的 RPC 策略。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1.  运行`\` *windir*`\system32\regedt32.exe`  
  
2.  找到并删除`HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`。  
  
3.  重新启动计算机以使注册表更改生效。  
  
4.  如果问题仍然存在，则与您的域管理员联系有关**计算机配置 > 管理模板 > 系统 > 远程过程调用 > 未经身份验证的 RPC 客户端的限制**组策略设置。