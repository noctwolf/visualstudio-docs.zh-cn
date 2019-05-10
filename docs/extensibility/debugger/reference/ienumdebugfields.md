---
title: IEnumDebugFields | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFields
helpviewer_keywords:
- IEnumDebugFields interface
ms.assetid: 403c2a51-3ba5-431f-a1dd-2f3b2046c00c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9cdb01a98a2cb2b2038366f0968c3b3532bd9ffc
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225585"
---
# <a name="ienumdebugfields"></a>IEnumDebugFields
此接口表示的对象实现的集合[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口。

## <a name="syntax"></a>语法

```
IEnumDebugFields : IUnknown
```

## <a name="notes-for-implementers"></a>实施者的说明
 此接口由符号提供程序来实现的对象集的实现[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口。 请注意，这不是由于存在一个标准 COM 枚举[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)方法。

## <a name="notes-for-callers"></a>调用方的说明
 此接口将返回由[GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)并[GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)。

## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法
 此接口实现以下方法。

|方法|描述|
|------------|-----------------|
|[下一页](../../../extensibility/debugger/reference/ienumdebugfields-next.md)|检索下一套[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)枚举中的对象。|
|[Skip](../../../extensibility/debugger/reference/ienumdebugfields-skip.md)|将跳过指定的数目的条目。|
|[Reset](../../../extensibility/debugger/reference/ienumdebugfields-reset.md)|将枚举重置为第一个条目。|
|[Clone](../../../extensibility/debugger/reference/ienumdebugfields-clone.md)|检索当前枚举的副本。|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugfields-getcount.md)|检索枚举中的条目数。|

## <a name="remarks"></a>备注

## <a name="requirements"></a>要求
 标头： sh.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [符号提供程序接口](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [GetMethodFieldsByName](../../../extensibility/debugger/reference/idebugsymbolprovider-getmethodfieldsbyname.md)
- [GetNamespacesUsedAtAddress](../../../extensibility/debugger/reference/idebugsymbolprovider-getnamespacesusedataddress.md)