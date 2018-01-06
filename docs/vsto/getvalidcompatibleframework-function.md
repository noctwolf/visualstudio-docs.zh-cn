---
title: "GetValidCompatibleFramework 函数 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: dfb365c0-5ffc-4290-ab8b-bd347e0f0db9
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: ee5a2ae08df4649d5e551973539321164d4a8e59
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getvalidcompatibleframework-function"></a>GetValidCompatibleFramework 函数
  此 API 支持 Office 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT WINAPI GetValidCompatibleFramework(  
    LPCWSTR lpwszCompatibleFrameworksXML,  
    BSTR* pbstrValidFrameworkTag  
);  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|*lpwszCompatibleFrameworksXML*|不要使用。|  
|*pbstrValidFrameworkTag*|不要使用。|  
  
## <a name="return-value"></a>返回值  
 如果函数成功，它将返回**，则为 S_OK**。 如果函数失败，则返回错误代码。  
  
  