---
title: 在中断模式中单步执行 |Microsoft Docs
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
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0721dcfe857f5c21aab634d02c29e864870c440b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478576"
---
# <a name="stepping-in-break-mode"></a>步入中断模式
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[单步执行在中断模式下](https://docs.microsoft.com/visualstudio/extensibility/debugger/stepping-in-break-mode)。  
  
下面介绍调试器处于中断模式下，必须单步执行代码时发生的过程：  
  
## <a name="stepping-process"></a>单步执行过程  
  
1.  调用[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)与[STEPKIND](../../extensibility/debugger/reference/stepkind.md)并[STEPUNIT](../../extensibility/debugger/reference/stepunit.md)自变量执行的步骤。  
  
2.  完成步骤后，发送[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md)为停止事件。  
  
## <a name="see-also"></a>请参阅  
 [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)

