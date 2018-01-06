---
title: "IDebugDynamicFieldCOMPlus |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugDynamicFieldCOMPlus interface
ms.assetid: c3a25f27-327a-4bdb-b026-27d436ddcd0c
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3f5f04c65e9e5799c759dd5a77d7158c98b9d46d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdynamicfieldcomplus"></a>IDebugDynamicFieldCOMPlus
表示有关动态字段[IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)对象。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugDynamicFieldCOMPlus : IDebugDynamicField  
```  
  
## <a name="methods"></a>方法  
 除了上的方法[IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md)接口，此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetTypeFromPrimitive](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus-gettypefromprimitive.md)|检索给定其基元类型的类型。|  
|[GetTypeFromTypeDef](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus-gettypefromtypedef.md)|检索给定标记的类型。|  
  
## <a name="requirements"></a>惠?  
 标头： Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll