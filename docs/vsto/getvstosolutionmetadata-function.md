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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e6289a0d19bc6621d98edfc974ad265791876a70
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "35671688"
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
  
  