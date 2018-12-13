---
title: IDebugPortPicker::DisplayPortPicker |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d05f49f8fa91a0b193be10169a4dcebcd561f92d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49910571"
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
  
#### <a name="parameters"></a>参数  
 `hwndParentDialog`  
 [in]父对话框的句柄。  
  
 `pbstrPortId`  
 [out]端口标识符字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 返回值`S_FALSE`(或返回值`S_OK`与`BSTR`设置为`NULL`) 指示用户单击**取消**。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)