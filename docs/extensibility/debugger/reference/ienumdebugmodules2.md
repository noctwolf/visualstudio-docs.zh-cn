---
title: IEnumDebugModules2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugModules2
helpviewer_keywords:
- IEnumDebugModules2
ms.assetid: 4fe28074-a960-41ad-b74d-b57f04c0c0ad
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 548bcd0328f7bdf52e47eb9a4295168ca47a2517
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65226702"
---
# <a name="ienumdebugmodules2"></a>IEnumDebugModules2
此接口枚举的模块的列表。

## <a name="syntax"></a>语法

```
IEnumDebugModules2 : IUnknown
```

## <a name="notes-for-implementers"></a>实施者的说明
 调试引擎 (DE) 实现此接口来表示某个程序的加载模块的列表。

## <a name="notes-for-callers"></a>调用方的说明
 Visual Studio 调用[EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)若要获取此接口。

## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法
 下表显示的方法`IEnumDebugModules2`。

|方法|描述|
|------------|-----------------|
|[下一页](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)|检索指定的枚举序列中的模块数。|
|[Skip](../../../extensibility/debugger/reference/ienumdebugmodules2-skip.md)|将跳过指定的数目的枚举序列中的模块。|
|[Reset](../../../extensibility/debugger/reference/ienumdebugmodules2-reset.md)|将枚举序列重置到开头。|
|[Clone](../../../extensibility/debugger/reference/ienumdebugmodules2-clone.md)|创建一个包含当前枚举数形式的相同枚举状态的枚举器。|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugmodules2-getcount.md)|获取模块的数。|

## <a name="remarks"></a>备注
 Visual Studio 将使用此接口主要用于更新**模块**窗口。

 为了在 Visual Studio 中进行调试，程序是可以跨越模块边界，因此代码说明一个逻辑序列的单个模块的列表需要[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)接口。 在列表中的第一个模块通常包含关联的程序的初始入口点。

## <a name="requirements"></a>要求
 标头： msdbg.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)