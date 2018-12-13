---
title: 错误： 无法启动 DCOM 通信 |Microsoft Docs
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
- vs.debug.error.unmarshal_server_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 2a7b27e6-2526-4f32-bc4d-eaee447f24ec
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 69fc98b18b89e3720340298500b44e62b621f0c4
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51807005"
---
# <a name="error-unable-to-initiate-dcom-communication"></a>错误：无法启动 DCOM 通信
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

当本地计算机尝试与远程计算机通信时，发生 DCOM 错误。 这是由于远程服务器上存在防火墙或远程计算机上的 Windows 身份验证已中断。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   如果远程计算机已启用 Windows 防火墙，请参阅[设置 Up the Remote Tools 在设备上](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)有关如何配置防火墙以便进行本地调试的说明。  
  
-   若要还原 Windows 身份验证，请尝试重新启动本地计算机和远程计算机。 检查本地和远程计算机上的事件日志以找出 Kerberos 错误，并与域管理员联系以了解已知问题。  
  
## <a name="see-also"></a>请参阅  
 [Remote Debugging](../debugger/remote-debugging.md)



