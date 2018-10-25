---
title: IDebugObject::GetValue |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject::GetValue
helpviewer_keywords:
- IDebugObject::GetValue method
ms.assetid: eec6051e-8ecb-49fa-bdd4-dd786f211692
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc7b0f063e64649a07954367105df6a20d997033
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49868412"
---
# <a name="idebugobjectgetvalue"></a>IDebugObject::GetValue
获取对象的值作为一系列连续的字节数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetValue(   
   BYTE* pValue,  
   UINT  nSize  
);  
```  
  
```csharp  
int GetValue(  
   ref byte[] pValue,   
   uint nSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pValue`  
 [in、 out]使用一系列连续的字节数表示的对象的值填充数组。  
  
 `nSize`  
 [in]要提取的字节数目上限。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 获取可以通过调用提取的值字节总数[GetSize](../../../extensibility/debugger/reference/idebugobject-getsize.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)