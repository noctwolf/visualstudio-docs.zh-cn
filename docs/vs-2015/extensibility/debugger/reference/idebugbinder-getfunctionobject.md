---
title: IDebugBinder::GetFunctionObject |Microsoft Docs
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
- IDebugBinder::GetFunctionObject
helpviewer_keywords:
- IDebugBinder::GetFunctionObject method
ms.assetid: 8fb789df-8f30-420d-8ca5-bb496a6738f1
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 901b1f046acf8d57d34bc2ce541dd944994626f8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480147"
---
# <a name="idebugbindergetfunctionobject"></a>IDebugBinder::GetFunctionObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugBinder::GetFunctionObject](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbinder-getfunctionobject)。  
  
此方法获取[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)对象，用于创建函数的参数。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetFunctionObject(   
   IDebugFunctionObject **ppFunction  
);  
```  
  
```csharp  
int GetFunctionObject(  
   out IDebugFunctionObject ppFunction  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppFunction`  
 [out]返回[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)用于创建函数参数的接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)

