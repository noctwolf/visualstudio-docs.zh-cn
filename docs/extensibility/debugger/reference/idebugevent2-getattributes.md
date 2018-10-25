---
title: IDebugEvent2::GetAttributes |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEvent2::GetAttributes
helpviewer_keywords:
- IDebugEvent2::GetAttributes
ms.assetid: 2ac5b5fb-da17-43f7-811a-313f677e60d7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 515775a064d1e260d9eb028c6e1b6020b7d642cd
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49935297"
---
# <a name="idebugevent2getattributes"></a>IDebugEvent2::GetAttributes
获取此调试事件的特性。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetAttribute(   
   DWORD* pdwAttrib  
);  
```  
  
```csharp  
int GetAttribute(   
   out uint pdwAttrib  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwAttrib`  
 [out]中的标志的组合[EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)枚举。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)接口是普遍适用于所有事件。 此方法描述类型的事件;例如，是同步还是异步事件并将它停止事件。  
  
## <a name="see-also"></a>请参阅  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)