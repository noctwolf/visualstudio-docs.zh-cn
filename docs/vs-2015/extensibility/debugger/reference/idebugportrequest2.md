---
title: IDebugPortRequest2 |Microsoft Docs
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
- IDebugPortRequest2
helpviewer_keywords:
- IDebugPortRequest2 interface
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7873d3d73556bae671cc1150525eb3d08a136e27
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483383"
---
# <a name="idebugportrequest2"></a>IDebugPortRequest2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugPortRequest2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportrequest2)。  
  
此接口描述一个端口。 此描述用于将端口添加到端口提供程序。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPortRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 Visual Studio 通常实现此接口从端口提供程序获取调试端口的过程中。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此接口传递到[端口](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)创建调试端口。 调用[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)返回此接口，表示用于第一个位置中创建该端口的请求。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugPortRequest2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|获取要创建的端口的名称。|  
  
## <a name="remarks"></a>备注  
 通常，调试引擎不与端口提供程序交互，并不会使用此接口。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [端口](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)   
 [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)

