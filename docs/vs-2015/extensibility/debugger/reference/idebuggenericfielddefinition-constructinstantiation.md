---
title: IDebugGenericFieldDefinition::ConstructInstantiation |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ConstructInstantiation
- IDebugGenericFieldDefinition::ConstructInstantiation
ms.assetid: ef8ae261-a98b-4dc2-93b3-7c5191818ba2
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8c5bd1d6164019414bc7cc299e418c38365dbc95
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483588"
---
# <a name="idebuggenericfielddefinitionconstructinstantiation"></a>IDebugGenericFieldDefinition::ConstructInstantiation
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugGenericFieldDefinition::ConstructInstantiation](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebuggenericfielddefinition-constructinstantiation)。  
  
构造给定类型的参数数组的字段实例。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT ConstructInstantiation(  
   ULONG32       cArgs,  
   IDebugField** ppArgs,  
   IDebugField** ppConstructedField  
);  
```  
  
```csharp  
int ConstructInstantiation(  
   uint            cArgs,  
   IDebugField[]   ppArgs,  
   out IDebugField ppConstructedField  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cArgs`  
 [in]中的参数数目`ppArgs`数组。  
  
 `ppArgs`  
 [in]包含的类型参数的数组。 类型参数必须为封闭的类型 （非泛型或完全实例化泛型）。  
  
 `ppConstructedField`  
 [out]返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口，表示新字段。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 不会检查约束。  
  
## <a name="see-also"></a>请参阅  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)

