---
title: IDebugPortSupplierEx2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortSupplierEx2 interface
ms.assetid: dae0050a-a50a-4f35-bfbd-e538f537b20f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a87ec52c3c7929d32da2b568b8e2735efc6319d8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56701402"
---
# <a name="idebugportsupplierex2"></a>IDebugPortSupplierEx2
为端口提供程序选择并核心服务器与之交互提供支持。

## <a name="syntax"></a>语法

```
IDebugPortSupplierEx2 : IUnknown
```

## <a name="notes-for-implementers"></a>实施者的说明
 自定义端口提供程序实现此接口，以便它可以选择要使用的核心服务器。

## <a name="methods"></a>方法
 下表显示的方法**IDebugPortSupplierEx2**。

|方法|描述|
|------------|-----------------|
|[SetServer](../../../extensibility/debugger/reference/idebugportsupplierex2-setserver.md)|设置端口提供程序的核心服务器。|

## <a name="requirements"></a>要求
 标头：Portpriv.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)