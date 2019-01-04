---
title: IDebugSymbolSearchEvent2::GetSymbolSearchInfo |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
helpviewer_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
ms.assetid: ae9eb72b-f2aa-43b8-87ca-da19d2e78d17
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f02eba47963dc39e7fa1fc426a762ff9f30a664d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53888694"
---
# <a name="idebugsymbolsearchevent2getsymbolsearchinfo"></a>IDebugSymbolSearchEvent2::GetSymbolSearchInfo
由事件处理程序来检索有关符号加载过程的结果调用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
   IDebugModule3**    pModule,  
   BSTR*              pbstrDebugMessage,  
   MODULE_INFO_FLAGS* pdwModuleInfoFlags  
);  
```  
  
```csharp  
int GetSymbolSearchInfo(  
   IDebugModule3              pModule,   
   ref string                 pbstrDebugMessage,   
   out enum_MODULE_INFO_FLAGS pdwModuleInfoFlags  
);  
  
```  
  
#### <a name="parameters"></a>参数  
 `pModule`  
 [out]一个表示已加载符号的模块 IDebugModule3 对象。  
  
 `pbstrDebugMessage`  
 [in、 out]返回一个包含模块中的任何错误消息的字符串。 如果没有错误，此字符串只包含模块的名称，但它也不为空。  
  
> [!NOTE]
>  [C + +]`pbstrDebugMessage`不能`NULL`并且必须释放与`SysFreeString`。  
  
 `pdwModuleInfoFlags`  
 [out]中的标志的组合[MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md)枚举，该值指示是否已加载任何符号。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。  
  
## <a name="remarks"></a>备注  
 当一个处理程序收到[IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)事件后尝试加载的模块的调试符号，该处理程序可以调用此方法来确定此类负载的结果。  
  
## <a name="see-also"></a>请参阅  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md)   
 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)