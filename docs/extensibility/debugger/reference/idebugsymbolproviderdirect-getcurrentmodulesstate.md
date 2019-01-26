---
title: IDebugSymbolProviderDirect::GetCurrentModulesState | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetCurrentModulesState
- IDebugSymbolProviderDirect::GetCurrentModulesState
ms.assetid: a0c85318-5686-4eed-b213-21f2b9e681e6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f53c36112ea2ac50406fb85b2b1099ed7220daf8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55022425"
---
# <a name="idebugsymbolproviderdirectgetcurrentmodulesstate"></a>IDebugSymbolProviderDirect::GetCurrentModulesState
检索有关符号该组符号提供程序是其成员之一的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCurrentModulesState(  
    DWORD*          pState,  
    unsigned long * count  
);  
```  
  
```csharp  
int GetCurrentModulesState(  
    out uint pState,  
    out uint count  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pState`  
 [out]符号提供程序组的状态。  
  
 `count`  
 [out]在组中的模块数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 每当添加或从符号组中删除模块时，更改状态。 因此，此方法可以用于检测是否已修改的符号组。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)