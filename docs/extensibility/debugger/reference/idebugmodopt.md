---
title: IDebugModOpt | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugModOpt interface
ms.assetid: ebd525e3-d140-4071-9d8c-41871de4125e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3e9a883c99bb41decbe0bbb53d2a4c484e021c07
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54929291"
---
# <a name="idebugmodopt"></a>IDebugModOpt
表示调试可选修饰符。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugModOpt : IUnknown  
```  
  
## <a name="notes-for-callers"></a>调用方的说明  
 从获取[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)表示类或方法的对象。  
  
## <a name="methods"></a>方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetModOpts](../../../extensibility/debugger/reference/idebugmodopt-getmodopts.md)|检索一组可选的修饰符。|  
  
## <a name="requirements"></a>要求  
 标头：Sh.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll