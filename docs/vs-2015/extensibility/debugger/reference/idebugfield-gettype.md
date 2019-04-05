---
title: IDebugField::GetType |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugField::GetType
helpviewer_keywords:
- IDebugField::GetType method
ms.assetid: b3cdec9f-ef7b-44d0-a775-d17ef7eae968
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d076b97ac777a56befdfa7d60a56361906ea3965
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58931931"
---
# <a name="idebugfieldgettype"></a>IDebugField::GetType
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此方法获取字段的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetType(   
   IDebugField** ppType  
);  
```  
  
```csharp  
int GetType(  
   out IDebugField ppType  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppType`  
 [out]返回的字段类型与另一个[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
