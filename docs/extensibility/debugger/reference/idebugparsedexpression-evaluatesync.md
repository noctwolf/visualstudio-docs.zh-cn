---
title: "IDebugParsedExpression::EvaluateSync |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugParsedExpression::EvaluateSync
helpviewer_keywords:
- IDebugParsedExpression::EvaluateSync method
ms.assetid: 0ea04cfa-de87-4b6c-897e-4572c1a28942
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 261359ae3dc82f8544d0f48cf0e8f1103ccedd5b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugparsedexpressionevaluatesync"></a>IDebugParsedExpression::EvaluateSync
此方法计算已分析的表达式，并 （可选） 将结果转换为另一种数据类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EvaluateSync(   
   DWORD                 dwEvalFlags,  
   DWORD                 dwTimeout,  
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   BSTR                  bstrResultType,  
   IDebugProperty2**     ppResult  
);  
```  
  
```csharp  
int EvaluateSync(  
   uint                 dwEvalFlags,   
   uint                 dwTimeout,   
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   string               bstrResultType,   
   out IDebugProperty2  ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwEvalFlags`  
 [in]组合[EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)控制如何计算表达式的常量。  
  
 `dwTimeout`  
 [in]指定以毫秒为单位，从此方法返回前等待的最长时间。 使用`INFINITE`无限期等待。  
  
 `pSymbolProvider`  
 [in]符号提供程序，表示为[IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)接口。  
  
 `pAddress`  
 [in]在方法中，表示为当前执行位置[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)接口。  
  
 `pBinder`  
 [in]联编程序，表示为[IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)接口。  
  
 `bstrResultType`  
 [in]结果的类型应强制转换为。 此参数可以是 null 值。  
  
 `ppResult`  
 [out]返回[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)表示评估的结果的接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 给定表达式评估上下文`pAddress`，从而无法确定包含方法和则使用语言作用域规则来确定在表达式中的符号的值。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)