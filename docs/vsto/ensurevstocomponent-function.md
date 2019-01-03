---
title: EnsureVSTOComponent 函数
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 88ed4de9f126f819f0cbdc7f3f49b4798ccb2195
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53838958"
---
# <a name="ensurevstocomponent-function"></a>EnsureVSTOComponent 函数
  此 API 支持 Office 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```csharp  
HRESULT EnsureVSTOComponent(  
    IVSTProject *pProject  
);  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|*pProject*|不要使用。|  
  
## <a name="return-value"></a>返回值  
 如果函数成功，它将返回 **，则为 S_OK**。 如果函数失败，则返回错误代码。  
