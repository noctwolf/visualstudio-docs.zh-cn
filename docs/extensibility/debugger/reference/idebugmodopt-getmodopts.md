---
title: IDebugModOpt::GetModOpts |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugModOpt::GetModOpts
- GetModOpts
ms.assetid: cb513fa9-d521-4a65-b968-f55f53a368df
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3ef054e35fe136b0b3280494b3dfd43cd58a53d5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53908236"
---
# <a name="idebugmodoptgetmodopts"></a>IDebugModOpt::GetModOpts
检索一组可选的修饰符。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetModOpts(  
   ULONG  celt,  
   BSTR*  rgelt,  
   ULONG* pceltFetched  
);  
```  
  
```csharp  
int GetModOpts(  
   uint         celt,  
   out string[] rgelt,  
   ref uint     pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]要返回的元素数。  
  
 `rgelt`  
 [out]返回一个数组，其中包含的选项。  
  
 `pceltFetched`  
 [in、 out]在返回的元素数目`rgelt`数组。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugModOpt](../../../extensibility/debugger/reference/idebugmodopt.md)