---
title: IDebugPortPicker::DisplayPortPicker |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 00923556927f2fed7e5895df2db391a45463e57e
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212903"
---
# <a name="idebugportpickerdisplayportpicker"></a>IDebugPortPicker::DisplayPortPicker
显示指定的对话框，允许用户选择的端口。

## <a name="syntax"></a>语法

```cpp
HRESULT DisplayPortPicker(
   HWND hwndParentDialog,
   BSTR* pbstrPortId
);
```

```csharp
public int DisplayPortPicker(
   int hwndParentDialog,
   out string pbstrPortId
);
```

## <a name="parameters"></a>参数
`hwndParentDialog`\
[in]父对话框的句柄。

`pbstrPortId`\
[out]端口标识符字符串。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。 返回值`S_FALSE`(或返回值`S_OK`与`BSTR`设置为`NULL`) 指示用户单击**取消**。

## <a name="see-also"></a>请参阅
- [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)