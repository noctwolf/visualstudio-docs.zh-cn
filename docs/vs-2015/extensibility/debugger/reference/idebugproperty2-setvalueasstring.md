---
title: IDebugProperty2::SetValueAsString |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProperty2::SetValueAsString
helpviewer_keywords:
- IDebugProperty2::SetValueAsString
ms.assetid: 9e6a5054-41b7-4223-b509-b93689d366a5
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f94ad530988ca354a1dd7618df0c7911987511e2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483685"
---
# <a name="idebugproperty2setvalueasstring"></a>IDebugProperty2::SetValueAsString
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProperty2::SetValueAsString](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty2-setvalueasstring)。  
  
从给定字符串中设置属性的值。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT SetValueAsString (   
   LPCOLESTR pszValue,  
   UINT      nRadix,  
   DWORD     dwTimeout  
);  
```  
  
```csharp  
int SetValueAsString (   
   string pszValue,  
   uint   nRadix,  
   uint   dwTimeout  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszValue`  
 [in]包含要设置的值的字符串。  
  
 `nRadix`  
 [in]用于解释任何数字信息的基数。 这可以是 0，以尝试自动确定基数。  
  
 `dwTimeout`  
 [in]指定以毫秒为单位，此方法返回前等待的最长时间。 使用`INFINITE`无限期等待。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。 下表显示了其他可能的值。  
  
|“值”|描述|  
|-----------|-----------------|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|字符串可以转换为属性值，或无法设置属性值。|  
|`E_SETVALUE_VALUE_IS_READONLY`|该属性是只读的。|  
  
## <a name="see-also"></a>请参阅  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)

