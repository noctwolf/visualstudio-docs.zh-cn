---
title: IDebugSettingsCallback2::EnumEEs |Microsoft Docs
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
- IDebugSettingsCallback2::EnumEEs
ms.assetid: 9f884c49-426f-461b-b547-9d909486e73f
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c435f658efb3bd926c476f6f2ed0f432f2f8b792
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51765237"
---
# <a name="idebugsettingscallback2enumees"></a>IDebugSettingsCallback2::EnumEEs
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

枚举给定语言和供应商标识符可用表达式计算器。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT EnumEEs(  
   DWORD  celtBuffer,  
   GUID*  rgguidLang,  
   GUID*  rgguidVendor,  
   DWORD* pceltEEs  
);  
```  
  
```csharp  
public int EnumEEs(  
   uint       celtBuffer,  
   ref Guid   rgguidLang,  
   ref Guid   rgguidVendor,  
   ref uint[] pceltEEs  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celtBuffer`  
 [in]中的元素数`pceltEEs`缓冲区。  
  
 `rgguidLang`  
 [in、 out]编程语言的唯一标识符。  
  
 `rgguidVendor`  
 [in、 out]供应商的唯一标识符。  
  
 `pceltEEs`  
 [in、 out]表达式计算器的数组。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)

