---
title: "IDebugEvent2::GetAttributes |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEvent2::GetAttributes
helpviewer_keywords: IDebugEvent2::GetAttributes
ms.assetid: 2ac5b5fb-da17-43f7-811a-313f677e60d7
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 117ca6867cef7f14de90213514a186662d1060b8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugevent2getattributes"></a>IDebugEvent2::GetAttributes
获取此调试事件的属性。  
  
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
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)接口是普遍适用于所有事件。 此方法描述事件; 的类型例如，是事件同步或异步，它停止事件。  
  
## <a name="see-also"></a>请参阅  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)