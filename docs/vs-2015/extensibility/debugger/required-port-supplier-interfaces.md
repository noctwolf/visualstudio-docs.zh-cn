---
title: 所需端口提供程序接口 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port suppliers, required interfaces
- debugging [Debugging SDK], port suppliers
ms.assetid: 0c2cdd40-9f6f-425e-b305-858f7734161e
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 960cd5668fe49ba50e79f036848948ec8e0bbfc2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472253"
---
# <a name="required-port-supplier-interfaces"></a>所需的端口提供程序接口
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[所需的端口提供程序接口](https://docs.microsoft.com/visualstudio/extensibility/debugger/required-port-supplier-interfaces)。  
  
端口提供程序必须实现[IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)接口。[IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)  
  
 由于端口提供程序都提供端口，它还必须实现它们。 因此，它必须实现以下接口：  
  
-   [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)  
  
     描述该端口和可枚举的端口上运行的所有进程。  
  
-   [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md)  
  
     提供用于启动和终止进程的端口上。  
  
-   [IDebugPortNotify2](../../extensibility/debugger/reference/idebugportnotify2.md)  
  
     提供了一种机制，通知程序节点创建和析构的此端口的上下文中运行的程序。 有关详细信息，请参阅[程序节点](../../extensibility/debugger/program-nodes.md)。  
  
-   `IConnectionPointContainer`  
  
     提供的连接点[IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md)。  
  
## <a name="port-supplier-operation"></a>端口供应商操作  
 [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md)接收器时接收通知过程和程序创建和销毁上一个端口。 发送所需的端口[IDebugProcessCreateEvent2](../../extensibility/debugger/reference/idebugprocesscreateevent2.md)时创建一个进程并[IDebugProcessDestroyEvent2](../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)端口上一个进程被销毁时。 一个端口也需要发送[IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)程序创建时和[IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)程序中的端口上运行的进程被销毁时。  
  
 端口通常发送程序创建和销毁事件以响应[AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)并[RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)方法，分别。  
  
 因为一个端口可以启动和终止进程的物理和逻辑的程序，还必须调试引擎中实现这些接口：  
  
-   [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)  
  
     介绍了物理过程。 至少必须实现以下方法：  
  
    -   [EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprocess2-getname.md)  
  
    -   [GetServer](../../extensibility/debugger/reference/idebugprocess2-getserver.md)  
  
    -   [GetPhysicalProcessId](../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
  
    -   [GetProcessId](../../extensibility/debugger/reference/idebugprocess2-getprocessid.md)  
  
    -   [GetAttachedSessionName](../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)  
  
-   [IDebugProcessEx2](../../extensibility/debugger/reference/idebugprocessex2.md)  
  
     提供有关 SDM，附加和分离本身从进程的方法。  
  
-   [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)  
  
     描述逻辑的程序。 至少必须实现以下方法：  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprogram2-getname.md)  
  
    -   [GetProcess](../../extensibility/debugger/reference/idebugprogram2-getprocess.md)  
  
    -   [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)  
  
-   [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)  
  
     提供有关 SDM，附加到此程序的方法。  
  
## <a name="see-also"></a>请参阅  
 [实现端口提供程序](../../extensibility/debugger/implementing-a-port-supplier.md)

