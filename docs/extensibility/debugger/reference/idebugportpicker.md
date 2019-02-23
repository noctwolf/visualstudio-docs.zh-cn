---
title: IDebugPortPicker | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortPicker interface
ms.assetid: 8b7f6685-a3c5-4355-b706-c1b574f6ff84
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 845e197b186d462b74aaf8cf3cd7218e4606dfc7
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56716540"
---
# <a name="idebugportpicker"></a>IDebugPortPicker
表示自定义的 UI 选择相应端口。

## <a name="syntax"></a>语法

```
IDebugPortPicker : IUnknown
```

## <a name="notes-for-implementers"></a>实施者的说明
 此接口由端口提供程序实现。 端口提供程序定义其端口选取器通过将其公开为 CLSID 并指向`metricPortPickerCLSID`指标在公开的 CLSID。

## <a name="methods"></a>方法
 下表显示的方法`IDebugPortPicker`。

|方法|描述|
|------------|-----------------|
|[DisplayPortPicker](../../../extensibility/debugger/reference/idebugportpicker-displayportpicker.md)|显示指定的对话框，允许用户选择的端口。|
|[SetSite](../../../extensibility/debugger/reference/idebugportpicker-setsite.md)|设置服务提供程序。|

## <a name="requirements"></a>要求
 标头：Msdbg.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll