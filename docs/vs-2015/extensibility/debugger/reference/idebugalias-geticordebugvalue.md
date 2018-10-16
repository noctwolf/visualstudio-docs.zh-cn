---
title: IDebugAlias::GetICorDebugValue |Microsoft Docs
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
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c5e67bf2c470fc525b2d918a5f4ecb10b13ff8d0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49306275"
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

检索表示与此别名关联的值的托管的代码接口。  
  
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
 [out]`IUnknown`接口，表示与此别名关联的值。 此接口可以查询有关`ICorDebugValue`接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法仅适用于托管值 (`ICorDebugValue`是一个接口中可用[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]中定义， [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] cordebug.idl 文件中的 SDK)。  
  
## <a name="see-also"></a>请参阅  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)

