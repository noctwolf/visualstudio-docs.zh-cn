---
title: 在中断模式下的表达式计算 |Microsoft Docs
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
- break mode, expression evaluation
- debugging [Debugging SDK], expression evaluation
- expression evaluation, break mode
ms.assetid: 34fe5b58-15d5-4387-a266-72120f90a4b6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a74119edfb390dab0a8ce0fddd96046ca80ad92d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484486"
---
# <a name="expression-evaluation-in-break-mode"></a>中断模式中的表达式计算
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[中断模式中的表达式计算](https://docs.microsoft.com/visualstudio/extensibility/debugger/expression-evaluation-in-break-mode)。  
  
以下介绍调试器处于中断模式下，必须执行表达式计算时，会发生的过程。  
  
## <a name="expression-evaluation-process"></a>表达式评估过程  
 以下是在计算表达式时所涉及的基本步骤：  
  
1.  会话调试管理器 (SDM) 调用[IDebugStackFrame2::GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)若要获取表达式上下文接口[IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md)。  
  
2.  然后调用 SDM [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)要分析的字符串。  
  
3.  如果 ParseText 不会返回 S_OK，则返回错误的原因。  
  
     -否则为-  
  
     如果 ParseText 不返回 S_OK，SDM 可以然后调用[IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)或[IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)以获取从分析得出的表达式的最终值。  
  
    -   对于使用`IDebugExpression2::EvaluateSync`，给定的回调接口用于通信的评估的持续的过程。 中返回的最终值[IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)接口。  
  
    -   对于使用`IDebugExpression2::EvaluateAsync`，给定的回调接口用于通信的评估的持续的过程。 评估完成后，将发送 EvaluateAsync [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)通过回调接口。 与此事件接口，最终值即可获得[GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md)。  
  
## <a name="see-also"></a>请参阅  
 [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)

