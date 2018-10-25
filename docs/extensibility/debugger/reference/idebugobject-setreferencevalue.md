---
title: IDebugObject::SetReferenceValue |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject::SetReferenceValue
helpviewer_keywords:
- IDebugObject::SetReferenceValue method
ms.assetid: 08c78a4e-98eb-41cb-8b75-02a6a43d49f7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1b597d7a62880e00a570a1971a6fec2becaaddca
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49908621"
---
# <a name="idebugobjectsetreferencevalue"></a>IDebugObject::SetReferenceValue
设置此对象的引用值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetReferenceValue(   
   IDebugObject* pObject  
);  
```  
  
```csharp  
int SetReferenceValue(  
   [In] IDebugObject pObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pObject`  
 [in][IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象，表示新的引用值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法使此[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象对中提供的对象的值的引用`pObject`参数，丢掉任何以前的引用。 请注意，此`IDebugObject`对象必须已是引用类型。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)