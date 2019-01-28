---
title: IDebugCustomAttribute::GetParentField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttribute::GetParentField
helpviewer_keywords:
- IDebugCustomAttribute::GetParentField
ms.assetid: bcdfdf37-bfcf-4988-a7b8-4c731d0af1b0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4a9f7987a2646b0235ffb266cf273704dce87c74
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55002498"
---
# <a name="idebugcustomattributegetparentfield"></a>IDebugCustomAttribute::GetParentField
获取自定义特性附加到的字段。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetParentField(   
   IDebugField** ppField  
);  
```  
  
```csharp  
int GetParentField(  
   out IDebugField ppField  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppField`  
 [out]返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)对象，表示自定义特性附加到的字段。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)方法返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)要确定哪些类型的字段的父对象。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)