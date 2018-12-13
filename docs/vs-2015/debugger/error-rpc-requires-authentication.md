---
title: 错误： RPC 要求身份验证 |Microsoft Docs
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
- vs.debug.error.rpc_requires_authentication
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 88362b3b-8fbe-431f-96a4-80e2d822bbc7
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a693b8ad331bbee5a920b0853f43ba521de2a105
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51806797"
---
# <a name="error-rpc-requires-authentication"></a>错误：RPC 要求身份验证
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 调试器无法连接到远程计算机。 本地计算机上启用了阻止远程调试的 RPC 策略。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1.  运行`\` *windir*`\system32\regedt32.exe`  
  
2.  找到并删除`HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`。  
  
3.  重新启动计算机以使注册表更改生效。  
  
4.  如果问题仍然存在，请联系您的域管理员**计算机配置-> 管理模板-> 系统-> 远程过程调用-> 的未经身份验证的 RPC 客户端限制**组策略设置。



