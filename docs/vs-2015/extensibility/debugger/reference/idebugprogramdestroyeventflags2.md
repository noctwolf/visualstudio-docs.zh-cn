---
title: IDebugProgramDestroyEventFlags2 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugProgramDestroyEventFlags2 interface
ms.assetid: d384ff71-dc71-40b9-a871-801f8b6a3418
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d062fe93a18b88cd6c24e0ece18d30f186c6420f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51777027"
---
# <a name="idebugprogramdestroyeventflags2"></a>IDebugProgramDestroyEventFlags2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

使调试引擎能够重写的默认行为[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]UI 时结束调试会话。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugProgramDestroyEventFlags2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 此接口由的调试引擎实现。 它可用于主机可能会创建和销毁进程的生存期内的多个程序。  
  
## <a name="methods"></a>方法  
 下表显示的方法`IDebugProgramDestroyEventFlags2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)|检索程序销毁标志。|  
  
## <a name="remarks"></a>备注  
 默认行为[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]UI 是以返回到设计模式下，所有程序具有都发送程序后销毁事件。 此接口使调试引擎，若要更改该行为。  
  
## <a name="requirements"></a>要求  
 标头： Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

