---
title: IDebugPortPicker |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugPortPicker interface
ms.assetid: 8b7f6685-a3c5-4355-b706-c1b574f6ff84
caps.latest.revision: 8
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 61973b6b9d7c62e8276f46443d0b9520419d3934
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportpicker"></a>IDebugPortPicker
表示自定义的 UI 选择端口。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPortPicker : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 通过端口供应商实现此接口。 端口供应商通过将其公开为 CLSID，并指向定义其端口选取器`metricPortPickerCLSID`公开 CLSID 在度量值。  
  
## <a name="methods"></a>方法  
 下表显示的方法`IDebugPortPicker`。  
  
|方法|描述|  
|------------|-----------------|  
|[DisplayPortPicker](../../../extensibility/debugger/reference/idebugportpicker-displayportpicker.md)|显示指定的对话框中，用户可以选择一个端口。|  
|[SetSite](../../../extensibility/debugger/reference/idebugportpicker-setsite.md)|设置服务提供程序。|  
  
## <a name="requirements"></a>惠?  
 标头： Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll