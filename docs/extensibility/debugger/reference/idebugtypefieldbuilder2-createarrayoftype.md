---
title: "IDebugTypeFieldBuilder2::CreateArrayOfType |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugTypeFieldBuilder2::CreateArrayOfType
- CreateArrayOfType
ms.assetid: 85166ac9-0bff-49a0-b2fd-ca7f7a8eae4b
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 907412ff68100f7669e6a51f90d7aae07994e628
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugtypefieldbuilder2createarrayoftype"></a>IDebugTypeFieldBuilder2::CreateArrayOfType
创建指定的类型和大小的数组。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateArrayOfType (  
   IDebugField*  pTypeField,  
   DWORD         rank,  
   IDebugField** pArrayOfTypeField  
);  
```  
  
```csharp  
int CreateArrayOfType (  
   IDebugField     pTypeField,  
   uint            rank,  
   out IDebugField pArrayOfTypeField  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pTypeField`  
 [in]该数组将容纳的元素的类型。  
  
 `rank`  
 [in]数组中的元素数目。  
  
 `pArrayOfTypeField`  
 [out]返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)表示新数组的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugTypeFieldBuilder2](../../../extensibility/debugger/reference/idebugtypefieldbuilder2.md)