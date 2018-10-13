---
title: IDebugMethodField::IsCustomAttributeDefined |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugMethodField::IsCustomAttributeDefined
helpviewer_keywords:
- IDebugMethodField::IsCustomAttributeDefined method
ms.assetid: 1b5d95a8-cc87-4acb-9e6a-3928f3632b7c
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2cd2a5e49b259cd1be8be530ade96e67e044cb4f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49230524"
---
# <a name="idebugmethodfieldiscustomattributedefined"></a>IDebugMethodField::IsCustomAttributeDefined
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

确定是否已定义特定的自定义属性。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT IsCustomAttributeDefined(   
   LPCOLESTR pszCustomAttributeName  
);  
```  
  
```csharp  
int IsCustomAttributeDefined(  
   [In] string pszCustomAttributeName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszCustomAttributeName`  
 [in]包含要查找的自定义属性的名称的字符串。  
  
## <a name="return-value"></a>返回值  
 返回 S_OK 如果自定义属性定义在此方法，否则，返回 S_FALSE。  
  
## <a name="see-also"></a>请参阅  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)

