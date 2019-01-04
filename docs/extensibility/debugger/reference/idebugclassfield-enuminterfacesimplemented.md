---
title: IDebugClassField::EnumInterfacesImplemented |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::EnumInterfacesImplemented
helpviewer_keywords:
- IDebugClassField::EnumInterfacesImplemented method
ms.assetid: e5523e45-d350-491e-a92c-fe0ca97d2052
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a58914186b09fe25fe67c8c6f914d3515615bd2a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53871026"
---
# <a name="idebugclassfieldenuminterfacesimplemented"></a>IDebugClassField::EnumInterfacesImplemented
创建此类实现的接口的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumInterfacesImplemented(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumInterfacesImplemented(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)表示列表的实现的接口的对象。 如果没有接口，则返回 null 值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK 或如果没有此类上实现接口，则返回 S_FALSE。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 枚举每个元素均[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)描述一个接口的对象。 请注意，非托管[!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)]以便此方法始终返回 null 值，对于非托管代码不作为离散实体使用接口[!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)]代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)