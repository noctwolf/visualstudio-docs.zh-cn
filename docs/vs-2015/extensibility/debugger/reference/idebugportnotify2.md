---
title: IDebugPortNotify2 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortNotify2
helpviewer_keywords:
- IDebugPortNotify2 interface
ms.assetid: 43278b79-bf16-4c08-bcf1-6f7f7a17feab
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e5bc329807d4b610ae42d3bb5ac5c95faf37db40
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51740390"
---
# <a name="idebugportnotify2"></a>IDebugPortNotify2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此接口注册或注销可以与它所在的端口进行调试的程序。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPortNotify2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 自定义端口提供程序实现此接口以支持添加和删除与该端口的程序。 它通常实现的相同对象上实现[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)接口。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)上`IDebugPort2`接口返回此接口。 此外，调用[GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)返回此接口。 调试引擎可以看到此接口的参数作为[WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugPortNotify2`。  
  
|方法|描述|  
|------------|-----------------|  
|[AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)|可调试的程序注册到的端口运行。|  
|[RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)|可以从其运行的端口进行调试的程序中注销。|  
  
## <a name="remarks"></a>备注  
 除非调试端口的方法可以知道加载或卸载程序时，自定义端口提供程序必须实现此接口。 使用此接口跟踪加载调试通过特定端口的所有程序。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)

