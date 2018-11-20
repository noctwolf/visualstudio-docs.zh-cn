---
title: IDebugCodeContext3 |Microsoft Docs
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
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8cbbec576b4e7b17f1a87e9d60ed1857fb3157b5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733260"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

扩展了[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)接口以便可以检索模块并处理的接口。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 由的调试引擎实现并由[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]调试包。  
  
## <a name="methods"></a>方法  
 除了上的方法`IDebugCodeContext2`接口，此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|检索到的调试模块接口的引用。|  
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|检索到的调试进程的接口的引用。|  
  
## <a name="remarks"></a>备注  
 这是通常不需要实现的可选接口。  
  
## <a name="requirements"></a>要求  
 标头： Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

