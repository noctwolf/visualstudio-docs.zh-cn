---
title: IDebugClassField::DoesInterfaceExist |Microsoft Docs
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
- IDebugClassField::DoesInterfaceExist
helpviewer_keywords:
- IDebugClassField::DoesInterfaceExist method
ms.assetid: cc0c8642-1a76-4fda-a309-7018a34883c9
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: af7c4db5d7515d9de49ab8ffda40acfda521a5df
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477896"
---
# <a name="idebugclassfielddoesinterfaceexist"></a>IDebugClassField::DoesInterfaceExist
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugClassField::DoesInterfaceExist](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugclassfield-doesinterfaceexist)。  
  
确定是否在类中定义的特定接口。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT DoesInterfaceExist(   
   LPCOLESTR pszInterfaceName  
);  
```  
  
```csharp  
int DoesInterfaceExist(  
   [In] string pszInterfaceName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszInterfaceName`  
 [in]包含要查找的接口名称的字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK，则返回 S_FALSE 接口不存在; 如果否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 实际上，此方法获取的所有接口的枚举，并搜索匹配的接口的列表。  
  
## <a name="see-also"></a>请参阅  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)

