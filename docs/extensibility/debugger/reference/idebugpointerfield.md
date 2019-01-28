---
title: IDebugPointerField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPointerField
helpviewer_keywords:
- IDebugPointerField interface
ms.assetid: d51bd5b2-f18e-4e27-b4fb-e6f652fbf635
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c2ef1b83dba8e35a1eee1c26090cc965b6afa41f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55015532"
---
# <a name="idebugpointerfield"></a>IDebugPointerField
此接口表示指针类型。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPointerField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 符号提供程序实现此接口来表示指针。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 使用[QueryInterface](/cpp/atl/queryinterface)若要获取此接口从[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口如果[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)返回`FIELD_TYPE_POINTER`。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 除了上的方法`IDebugField`和`IDebugContainerField`接口，此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetDereferencedField](../../../extensibility/debugger/reference/idebugpointerfield-getdereferencedfield.md)|返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)描述目标的指针。|  
  
## <a name="remarks"></a>备注  
 C/c + + 中，如果在使用数组表示法，指针可以为一个容器。 例如，给定`char *pString`，`pString`的类型为指向`char`。 `pString[3]` 具有类型是指向指针的容器的`char`引用该容器的第四个元素。  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [符号提供程序接口](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)