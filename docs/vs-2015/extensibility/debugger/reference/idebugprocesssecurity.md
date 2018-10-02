---
title: IDebugProcessSecurity |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugProcessSecurity interface
ms.assetid: 8a52ddca-bd99-49c0-9778-469dce7abd44
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c3cfa0d8ef0f43b21ec2057b71b688b2d3ecb66
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470795"
---
# <a name="idebugprocesssecurity"></a>IDebugProcessSecurity
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProcessSecurity](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocesssecurity)。  
  
`IDebugProcessSecurity` 被实现端口提供程序来警告用户，附加到进程是不安全的。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugProcessSecurity : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugProcessSecurity`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetUserName](../../../extensibility/debugger/reference/idebugprocesssecurity-getusername.md)|从端口提供程序获取用户名称。|  
|[QueryCanSafelyAttach](../../../extensibility/debugger/reference/idebugprocesssecurity-querycansafelyattach.md)|警告用户将附加到调试过程是不安全。|  
  
## <a name="remarks"></a>备注  
 实现此接口可显示一条警告，并允许用户取消如果要附加的过程可被视为不安全。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [端口](../../../extensibility/debugger/ports.md)   
 [端口提供程序](../../../extensibility/debugger/port-suppliers.md)   
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

