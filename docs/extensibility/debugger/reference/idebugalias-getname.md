---
title: IDebugAlias::GetName |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugAlias::GetName
helpviewer_keywords:
- IDebugAlias::GetName method
ms.assetid: ac2d8891-56b5-40ef-9866-ed74f18bb043
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9b6a67db70e1913f44d47dbc629b66d43d4062ac
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49916512"
---
# <a name="idebugaliasgetname"></a>IDebugAlias::GetName
获取此别名的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetName(  
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetName(  
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrName`  
 [out]别名的名称。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)