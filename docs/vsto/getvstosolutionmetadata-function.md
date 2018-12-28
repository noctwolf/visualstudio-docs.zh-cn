---
title: GetVstoSolutionMetadata 函数
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: baa5cf48d317da80f78d19a1b72f81824b1bed62
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2018
ms.locfileid: "53647260"
---
# <a name="getvstosolutionmetadata-function"></a>GetVstoSolutionMetadata 函数
  此 API 支持 Office 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```csharp
HRESULT WINAPI GetVstoSolutionMetadata(  
    LPCWSTR lpwszSolutionMetadataKey,  
    ISolutionMetadata** ppSolutionInfo  
);  
```  
  
### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|*lpwszSolutionMetadataKey*|不要使用。|  
|*ppSolutionInfo*|不要使用。|  
  
## <a name="return-value"></a>返回值  
 如果函数成功，它将返回 **，则为 S_OK**。 如果函数失败，则返回错误代码。  
  
  