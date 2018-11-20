---
title: IDebugSettingsCallback2::GetEELocalObject |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugSettingsCallback2::GetEELocalObject
ms.assetid: e69a3469-a049-420c-b918-c48a1e7b9baf
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 14ee687700aadb4eff0ab4fa160cf8ac339de54b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51769855"
---
# <a name="idebugsettingscallback2geteelocalobject"></a>IDebugSettingsCallback2::GetEELocalObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

检索给定的指标名称的表达式计算器本地对象。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetEELocalObject(  
   REFGUID     guidLang,  
   REFGUID     guidVendor,  
   LPCWSTR     pszMetric,  
   IUnknown ** ppUnk  
);  
```  
  
```csharp  
private int GetEELocalObject(  
   ref Guid          guidLang,  
   ref Guid          guidVendor,  
   string            pszMetric,  
   out System.Object ppUnk  
);  
```  
  
#### <a name="parameters"></a>参数  
 `guidLang`  
 [in]编程语言的唯一标识符。  
  
 `guidVendor`  
 [in]供应商的唯一标识符。  
  
 `pszMetric`  
 [in]指标的名称。  
  
 `ppUnk`  
 [out]返回的表达式计算器本地对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)

