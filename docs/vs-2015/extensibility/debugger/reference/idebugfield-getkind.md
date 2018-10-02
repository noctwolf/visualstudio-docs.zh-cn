---
title: IDebugField::GetKind |Microsoft Docs
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
- IDebugField::GetKind
helpviewer_keywords:
- IDebugField::GetKind method
ms.assetid: e7c9c60a-8e55-4ecc-aa63-0c814a1e92cc
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3bdf20ff027253a5d98e6e3e69bbc11897ec4116
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482526"
---
# <a name="idebugfieldgetkind"></a>IDebugField::GetKind
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugField::GetKind](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfield-getkind)。  
  
此方法获取字段的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetKind(   
   FIELD_KIND* pdwKind  
);  
```  
  
```csharp  
int GetKind(  
   out enum_FIELD_KIND pdwKind  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwKind`  
 [out]返回的字段类型的组合[FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)常量。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)

