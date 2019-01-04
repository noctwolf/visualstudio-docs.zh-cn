---
title: IDebugExpression2::EvaluateSync |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugExpression2::EvaluateSync
helpviewer_keywords:
- IDebugExpression2::EvaluateSync
ms.assetid: 88964915-dce3-4005-b4f3-9f37415e41e4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 48e72b61f6d7504572ebcf5e9bed4be062307ed1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53850760"
---
# <a name="idebugexpression2evaluatesync"></a>IDebugExpression2::EvaluateSync
此方法以同步方式计算的表达式。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EvaluateSync(   
   EVALFLAGS             dwFlags,  
   DWORD                 dwTimeout,  
   IDebugEventCallback2* pExprCallback,  
   IDebugProperty2**     ppResult  
);  
```  
  
```csharp  
int EvaluateSync(  
   enum_EVALFLAGS       dwFlags,   
   uint                 dwTimeout,   
   IDebugEventCallback2 pExprCallback,   
   out IDebugProperty2  ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwFlags`  
 [in]中的标志的组合[EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)控制表达式求值的枚举。  
  
 `dwTimeout`  
 [in]最大时间 （毫秒），此方法返回前等待。 使用`INFINITE`无限期等待。  
  
 `pExprCallback`  
 [in]此参数始终是一个 null 值。  
  
 `ppResult`  
 [out]返回[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)对象，其中包含的表达式计算结果。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。 一些典型的错误代码为：  
  
|Error|描述|  
|-----------|-----------------|  
|E_EVALUATE_BUSY_WITH_EVALUATION|当前正在计算另一个表达式，并且不支持同时表达式计算。|  
|E_EVALUATE_TIMEOUT|计算已超时。|  
  
## <a name="remarks"></a>备注  
 对于同步的计算，不需要返回到 Visual Studio 评估完成后发送事件。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于简单`CExpression`对象，它实现[IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)接口。  
  
```cpp  
HRESULT CExpression::EvaluateSync(EVALFLAGS dwFlags,  
                                  DWORD dwTimeout,  
                                  IDebugEventCallback2* pExprCallback,  
                                  IDebugProperty2** ppResult)  
{  
    // Set the aborted state to FALSE.    
    m_bAborted = FALSE;    
    // Delegate the evaluation to EvalExpression.    
    return EvalExpression(TRUE, ppResult);    
}  
  
HRESULT CExpression::EvalExpression(BOOL bSynchronous,  
                                    IDebugProperty2** ppResult)  
{  
    HRESULT hr;  
  
    // Get the value of an environment variable.  
    PCSTR pszVal = m_pEnvBlock->GetEnv(m_pszVarName);  
    // Create and initialize a CEnvVar object with the retrieved value.  
    // CEnvVar implements the IDebugProperty2 interface.  
    CComObject<CEnvVar> *pEnvVar;  
    CComObject<CEnvVar>::CreateInstance(&pEnvVar);  
    pEnvVar->Init(m_pszVarName, pszVal, m_pDoc);  
  
    if (pszVal) {  
        // Check for synchronous evaluation.  
        if (bSynchronous) {  
            // Set and AddRef the result, IDebugProperty2 interface.  
            *ppResult = pEnvVar;  
            (*ppResult)->AddRef();  
            hr = S_OK;  
        } else {  
            //For asynchronous evaluation, send an evaluation complete event.  
            CExprEvalEvent *pExprEvent = new CExprEvalEvent(this, pEnvVar);  
            pExprEvent->SendEvent(m_pExprCallback, NULL, NULL, NULL);  
        }  
    } else {  
        // If a valid value is not retrieved, return E_FAIL.  
        hr = E_FAIL;  
    }  
    return hr;  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)   
 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)