---
title: IDebugSettingsCallback2::GetMetricGuid |Microsoft Docs
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
- IDebugSettingsCallback2::GetMetricGuid
ms.assetid: 91092763-3362-4857-adf0-231bc1254206
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 48662b00dc168e44e6d1c8e5fb473e716e423304
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481233"
---
# <a name="idebugsettingscallback2getmetricguid"></a>IDebugSettingsCallback2::GetMetricGuid
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugSettingsCallback2::GetMetricGuid](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugsettingscallback2-getmetricguid)。  
  
检索在给定名称的一个指标的唯一标识符。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetMetricGuid(  
   LPCWSTR pszType,  
   REFGUID guidSection,  
   LPCWSTR pszMetric,  
   GUID*   pguidValue  
);  
```  
  
```csharp  
private int GetMetricGuid(  
   string   pszType,  
   ref Guid guidSection,  
   string   pszMetric,  
   out Guid pguidValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszType`  
 [in]该度量值的类型。  
  
 `guidSection`  
 [in]部分中的唯一标识符。  
  
 `pszMetric`  
 [in]指标的名称。  
  
 `pguidValue`  
 [out]返回度量值的唯一标识符。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)

