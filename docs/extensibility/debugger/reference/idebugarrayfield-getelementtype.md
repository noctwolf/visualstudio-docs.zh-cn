---
title: "IDebugArrayField::GetElementType |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugArrayField::GetElementType
helpviewer_keywords: IDebugArrayField::GetElementType method
ms.assetid: c46bf625-0a48-4cbb-8f1f-286356f2c065
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 46a2a3066a84c78d08e07fab0c7da394acd2bb64
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugarrayfieldgetelementtype"></a>IDebugArrayField::GetElementType
获取数组中元素的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetElementType(   
   IDebugField** ppType  
);  
```  
  
```csharp  
int GetElementType(  
   out IDebugField ppType  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppType`  
 [out]返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)描述元素的类型的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)对象假定数组的所有元素都具有相同的类型。  
  
## <a name="see-also"></a>请参阅  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)