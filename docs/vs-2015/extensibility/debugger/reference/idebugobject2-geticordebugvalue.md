---
title: IDebugObject2::GetICorDebugValue |Microsoft Docs
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
- IDebugObject2::GetICorDebugValue
helpviewer_keywords:
- IDebugObject2::GetICorDebugValue method
ms.assetid: bcd4355d-3fbe-483f-bb23-a44348323c6a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cc91846d7ee68ec7381d552c4cb8c1c85128490b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472195"
---
# <a name="idebugobject2geticordebugvalue"></a>IDebugObject2::GetICorDebugValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugObject2::GetICorDebugValue](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject2-geticordebugvalue)。  
  
获取表示与此对象关联的值的托管的代码对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetICorDebugValue(  
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetICorDebugValue(  
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppUnk`  
 [out]`IUnknown`接口，表示此别名。 此接口可以查询有关`ICorDebugValue`接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 `ICorDebugValue`对象是一个公共语言运行时接口，表示的值。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)

