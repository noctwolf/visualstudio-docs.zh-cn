---
title: IDebugSettingsCallback2::GetMetricString | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::GetMetricString
- GetMetricString
ms.assetid: ecc875a2-8ac6-444c-a839-5191a780fd6b
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f20348cdced520b4153f02d2320fcabcd266273d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58933727"
---
# <a name="idebugsettingscallback2getmetricstring"></a>IDebugSettingsCallback2::GetMetricString
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

检索在给定名称的度量值的值字符串。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetMetricString(  
    LPCWSTR pszType,  
    REFGUID guidSection,  
    LPCWSTR pszMetric,  
    BSTR*   pbstrValue  
);  
```  
  
```csharp  
private int GetMetricString(  
    string     pszType,  
    ref Guid   guidSection,  
    string     pszMetric,  
    out string pbstrValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszType`  
 [in]该度量值的类型。  
  
 `guidSection`  
 [in]部分中的唯一标识符。  
  
 `pszMetric`  
 [in]指标的名称。  
  
 `pbstrValue`  
 [out]返回度量值的值字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)
