---
title: EnsureVSTOComponent 函数
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
ms.openlocfilehash: 20c4e363b11647609b67a898878dd4b4e59ba180
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2018
---
# <a name="ensurevstocomponent-function"></a>EnsureVSTOComponent 函数
  此 API 支持 Office 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```c  
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
  
  