---
title: IDebugAddress2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugAddress2
helpviewer_keywords:
- IDebugAddress2 interface
ms.assetid: b150e0ed-4ac0-4f8c-9732-4b3e54b9d243
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9bb2f2b35865f423b4405738260976ab19308eab
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54920664"
---
# <a name="idebugaddress2"></a>IDebugAddress2
此接口提供访问该对象所属的地址的进程 ID 表示通过此接口。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugAddress2 : IDebugAddress  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 符号提供程序实现此接口上实现的相同对象[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)接口。 此接口提供对拥有此地址与相关的对象的进程的 ID 的访问。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 使用[QueryInterface](/cpp/atl/queryinterface)若要获取此接口从[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 除了继承的方法之外[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)接口，此接口实现了以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetProcessID](../../../extensibility/debugger/reference/idebugaddress2-getprocessid.md)|检索拥有该接口表示的对象的进程的 ID。|  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [符号提供程序接口](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)