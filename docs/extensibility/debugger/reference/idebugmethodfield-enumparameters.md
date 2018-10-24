---
title: IDebugMethodField::EnumParameters |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7405b451a29af71a2cad3ad3e4a36692737d8d53
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49910454"
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
创建方法的参数的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppParams`  
 [out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)表示方法的参数列表的对象; 否则，返回 null 值，如果任何参数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK 或如果没有任何参数，则返回 S_FALSE。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 每个元素均[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)对象，表示不同类型的参数。 调用[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)来确定完全什么类型的参数对象表示的每个对象的方法。  
  
 参数包括其变量名称和它的类型。 类方法的第一个参数通常是"this"指针。  
  
 如果只需要参数的类型，则调用[EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)