---
title: IDebugCustomAttributeQuery2::EnumCustomAttributes |Microsoft Docs
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
- IDebugCustomAttributeQuery2::EnumCustomAttributes
helpviewer_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
ms.assetid: 94bfce74-aa3d-45f0-8e04-5715faf85217
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b889c21c5822761fe32cacaf725ddba4812dc2f3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49213455"
---
# <a name="idebugcustomattributequery2enumcustomattributes"></a>IDebugCustomAttributeQuery2::EnumCustomAttributes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取附加到此字段的所有自定义属性的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT EnumCustomAttributes(   
   IEnumDebugCustomAttributes** ppEnum  
);  
```  
  
```csharp  
int EnumCustomAttributes(  
   out IEnumDebugCustomAttributes ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]返回[IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)对象，表示自定义特性列表; 否则，返回 null 值，如果没有自定义属性。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回 S_OK 或 S_FALSE 如果在此字段上没有任何自定义属性。 否则，返回错误代码;  
  
## <a name="remarks"></a>备注  
 字段可以包含多个自定义属性。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)

