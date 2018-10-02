---
title: IDebugProviderProgramNode2 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProviderProgramNode2
helpviewer_keywords:
- IDebugProviderProgramNode2
ms.assetid: f0bca1cc-afbe-44cf-b5aa-d078aa685d24
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b4b180ad9ceb0ccb44a04f4f06af3541d2244822
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472265"
---
# <a name="idebugproviderprogramnode2"></a>IDebugProviderProgramNode2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProviderProgramNode2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproviderprogramnode2)。  
  
此接口将跨进程边界封送与程序相关的接口。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugProviderProgramNode2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 调试引擎 (DE) 实现此接口上实现的相同对象[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)以支持跨进程边界封送处理的接口。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)上`IDebugProgramNode2`接口，以获得此接口。 如果无法获取此接口，DE 不支持的接口封送处理。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[UnmarshalDebuggeeInterface](../../../extensibility/debugger/reference/idebugproviderprogramnode2-unmarshaldebuggeeinterface.md)|获取跨进程边界的指定的接口。|  
  
## <a name="remarks"></a>备注  
 DE 在单独的进程空间中运行从正在调试的程序时实现此接口： 例如，DE 运行时在 Visual Studio 进程空间而不是正在调试的程序的进程空间中。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)

