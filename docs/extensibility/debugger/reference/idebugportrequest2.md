---
title: "IDebugPortRequest2 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortRequest2
helpviewer_keywords: IDebugPortRequest2 interface
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5b47a9bde47049c957af9f60e1d09d03b55c2359
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportrequest2"></a>IDebugPortRequest2
此接口描述一个端口。 此说明用于将端口添加到端口供应商。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPortRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 Visual Studio 通常实现此接口过程中从端口提供程序获取调试端口。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此接口传递到[添加](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)以创建调试端口。 调用[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)返回此接口，表示用于第一个位置创建该端口的请求。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugPortRequest2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|获取要创建的端口的名称。|  
  
## <a name="remarks"></a>备注  
 通常，调试引擎不与端口提供程序交互，并且将具有无需使用此接口。  
  
## <a name="requirements"></a>惠?  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [添加](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)   
 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)