---
title: IDebugModOpt |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugModOpt interface
ms.assetid: ebd525e3-d140-4071-9d8c-41871de4125e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0477f8b3a39bd919a814828377228c5ccc02bd11
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31112390"
---
# <a name="idebugmodopt"></a>IDebugModOpt
表示调试的可选修饰符。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugModOpt : IUnknown  
```  
  
## <a name="notes-for-callers"></a>调用方的说明  
 从获取[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)表示一个类或方法的对象。  
  
## <a name="methods"></a>方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetModOpts](../../../extensibility/debugger/reference/idebugmodopt-getmodopts.md)|检索可选修饰符的列表。|  
  
## <a name="requirements"></a>要求  
 标头： Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll