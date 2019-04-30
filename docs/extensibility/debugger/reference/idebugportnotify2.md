---
title: IDebugPortNotify2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortNotify2
helpviewer_keywords:
- IDebugPortNotify2 interface
ms.assetid: 43278b79-bf16-4c08-bcf1-6f7f7a17feab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2427bfbc70c992cfcd41217aec56aa94d825faae
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62918164"
---
# <a name="idebugportnotify2"></a>IDebugPortNotify2
此接口注册或注销可以与它所在的端口进行调试的程序。

## <a name="syntax"></a>语法

```
IDebugPortNotify2 : IUnknown
```

## <a name="notes-for-implementers"></a>实施者的说明
 自定义端口提供程序实现此接口以支持添加和删除与该端口的程序。 它通常实现的相同对象上实现[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)接口。

## <a name="notes-for-callers"></a>调用方的说明
 调用[QueryInterface](/cpp/atl/queryinterface)上`IDebugPort2`接口返回此接口。 此外，调用[GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)返回此接口。 调试引擎可以看到此接口的参数作为[WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)。

## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法
 下表显示的方法`IDebugPortNotify2`。

|方法|描述|
|------------|-----------------|
|[AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)|可调试的程序注册到的端口运行。|
|[RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)|可以从其运行的端口进行调试的程序中注销。|

## <a name="remarks"></a>备注
 除非调试端口的方法可以知道加载或卸载程序时，自定义端口提供程序必须实现此接口。 使用此接口跟踪加载调试通过特定端口的所有程序。

## <a name="requirements"></a>要求
 标头： msdbg.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)