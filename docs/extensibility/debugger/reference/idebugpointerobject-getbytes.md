---
title: IDebugPointerObject::GetBytes |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPointerObject::GetBytes
helpviewer_keywords:
- IDebugPointerObject::GetBytes method
ms.assetid: e986c188-87fb-4b51-86e9-ee6a0035bdab
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1459a0f99dd4b0ea9c9e998404b1ffe1733cb3bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31115861"
---
# <a name="idebugpointerobjectgetbytes"></a>IDebugPointerObject::GetBytes
获取指向作为一系列连续字节的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetBytes(   
   DWORD  dwStart,  
   DWORD  dwCount,  
   BYTE*  pBytes,  
   DWORD* pdwBytes  
);  
```  
  
```csharp  
int GetBytes(  
   uint       dwStart,   
   uint       dwCount,   
   out byte[] pBytes,   
   out uint   pdwBytes  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwStart`  
 [in]偏移量，以字节为单位的开始处指向的对象。  
  
 `dwCount`  
 [in]要检索的字节数。  
  
 `pBytes`  
 [在中，out]指向为一系列连续字节的情况下使用的值填充的数组，该对象从给定的偏移量处开始。  
  
 `pdwBytes`  
 [out]返回实际检索的字节的数。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果使用此方法的指针所表示的这[IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)指向基元类型或基元类型 （即，可以通过简单的序列的字节来表示一个数组） 的简单的数组。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)   
 [SetBytes](../../../extensibility/debugger/reference/idebugpointerobject-setbytes.md)