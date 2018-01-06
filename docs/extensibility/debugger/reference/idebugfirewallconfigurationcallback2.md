---
title: "IDebugFirewallConfigurationCallback2 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugFirewallConfigurationCallback2 interface
ms.assetid: 0827361c-b97c-4851-9898-ab6d88c81811
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 02996f28ca502359d9a2d71cfbf11a913f2bf51e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfirewallconfigurationcallback2"></a>IDebugFirewallConfigurationCallback2
启用调试引擎，使用 DCOM 询问[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]UI，以确保该防火墙将阻止远程调试。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugFirewallConfigurationCallback2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 端口对象的会话调试管理器实现。  
  
## <a name="methods"></a>方法  
 下表显示的方法`IDebugFirewallConfigurationCallback2`。  
  
|方法|描述|  
|------------|-----------------|  
|[EnsureDCOMUnblocked](../../../extensibility/debugger/reference/idebugfirewallconfigurationcallback2-ensuredcomunblocked.md)|该防火墙不阻止远程调试的请求。|  
  
## <a name="requirements"></a>惠?  
 标头： Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll