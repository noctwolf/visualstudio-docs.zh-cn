---
title: 端口 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ports
- debugging [Debugging SDK], ports
ms.assetid: 1d7f3aa7-7eff-4cab-bc53-0a566b1a9363
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d6a73aef5151b12360d1e227d440223df4ff3298
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251044"
---
# <a name="ports"></a>端口
在调试器体系结构中，*端口*:  
  
-   服务器上运行的进程组的容器。 例如，端口可能表示连接到基于 Windows CE 的设备的串行电缆或网络的非 DCOM 计算机。 一个特殊的端口，称为本地端口，包含在本地计算机上运行的所有进程。  
  
-   可以将自己标识的名称或标识符。  
  
-   可枚举的端口上运行的所有进程和启动并终止这些进程。  
  
-   为由[IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)接口，通过将传递创建[IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)参数[端口](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)。  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 提供了处理所有基于 Windows 的进程，本机和托管的默认端口。 自定义端口必须是连接与设置不是基于 Windows 的外部设备。 若要提供此类自定义端口，必须还设置自定义端口提供程序。  
  
## <a name="see-also"></a>请参阅  
 [服务器](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [进程](../../extensibility/debugger/processes.md)   
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)   
 [端口](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)