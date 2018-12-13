---
title: IDebugEngine3::SetJustMyCodeState |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine3::SetJustMyCodeState
helpviewer_keywords:
- IDebugEngine3::SetJustMyCodeState
ms.assetid: 8ec17fbf-df93-424a-b2ed-fd1e5ee51256
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ffad3e6be4d81e19bd6f707bd30c744904217ba5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49928966"
---
# <a name="idebugengine3setjustmycodestate"></a>IDebugEngine3::SetJustMyCodeState
此方法的 JustMyCode 状态信息中介绍的调试引擎。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetJustMyCodeState(  
   BOOL           fUpdate,  
   DWORD          dwModules,  
   JMC_CODE_SPEC* rgJMCSpec  
);  
```  
  
```csharp  
int SetJustMyCodeState(  
   int             fUpdate,   
   uint            dwModules,   
   JMC_CODE_SPEC[] rgJMCSpec  
);  
```  
  
#### <a name="parameters"></a>参数  
 `fUpdate`  
 [in]非零值 (`TRUE`) 以更新当前的信息，请为零 (`FALSE`) 重置 （忽略任何内容之前设置） 的所有信息。  
  
 `dwModules`  
 [in]中的信息结构的数目 `rgJMCSpec.`  
  
 `rgJMCSpec`  
 [in]数组[JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md)结构使用。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为将返回错误代码。  
  
## <a name="remarks"></a>备注  
 JustMyCode 是调试仅属于用户的代码并忽略所有中间代码，如系统代码的概念，即使该系统代码提供了源代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)   
 [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md)