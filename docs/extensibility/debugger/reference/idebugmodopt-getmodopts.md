---
title: IDebugModOpt::GetModOpts | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugModOpt::GetModOpts
- GetModOpts
ms.assetid: cb513fa9-d521-4a65-b968-f55f53a368df
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c611c55654ee14bc3cda3f27fe20e19188faa71a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55017158"
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