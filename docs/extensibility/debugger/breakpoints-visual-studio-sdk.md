---
title: 断点 (Visual Studio SDK) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- breakpoints
ms.assetid: acfcabed-9f2f-436c-ad18-7ca2f45d631b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a2898a78971eaf20abe89274a1492afb343edfbb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54919390"
---
# <a name="breakpoints-visual-studio-sdk"></a>断点 (Visual Studio SDK)
有三种类型的断点： 挂起、 绑定和错误。  
  
 **挂起断点的一个：**  
  
- 是包含要将断点绑定到一个或多个程序中的一个或多个代码上下文所需的所有信息的抽象。 每次调试引擎程序正在调试用于加载的原因代码，检查所有挂起断点，以查看是否可以将它们绑定。  
  
   挂起断点本身永远不会将绑定到代码中，但而不是收集，则称其包含它生成的所有绑定的断点。  
  
- 为由[IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)接口。  
  
  **绑定的断点：**  
  
- 断点的抽象与关联或绑定到单个代码上下文。 每个绑定的断点生成了挂起断点的响应。 挂起断点可以但是，生成多个绑定的断点。  
  
   卸载代码时，可以将未绑定的绑定的断点并将其丢弃。  
  
- 为由[IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)接口。  
  
  **错误断点：**  
  
- 是在尝试将挂起断点绑定到代码上下文描述错误的抽象。 错误断点任一错误在位置，或者在该断点表达式本身中进行描述。 有关详细信息，请参阅[绑定断点](../../extensibility/debugger/binding-breakpoints.md)。  
  
   断点错误可以是错误或警告。  
  
- 为由[IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)接口。  
  
## <a name="see-also"></a>请参阅  
 [程序](../../extensibility/debugger/programs.md)   
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)   
 [代码上下文](../../extensibility/debugger/code-context.md)   
 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)