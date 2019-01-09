---
title: IDebugApplication::RemoveGlobalExpressionContextProvider |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.RemoveGlobalExpressionContextProvider
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::RemoveGlobalExpressionContextProvider
ms.assetid: ace638a3-ed34-4d20-8404-45c684aaaf1a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5038d85e48b6735c81977d20f295dd4e0868e2e2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093881"
---
# <a name="idebugapplicationremoveglobalexpressioncontextprovider"></a>IDebugApplication::RemoveGlobalExpressionContextProvider
此应用程序中删除全局表达式上下文提供程序。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT RemoveGlobalExpressionContextProvider(  
   DWORD_PTR  dwCookie  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwCookie`  
 [in]返回的 cookie`AddGlobalExpressionContextProvider`方法添加的全局上下文提供程序时。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 `RemoveGlobalExpressionContextProvider`方法从该应用程序中删除全局表达式上下文提供程序。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplication::AddGlobalExpressionContextProvider](../../winscript/reference/idebugapplication-addglobalexpressioncontextprovider.md)   
 [IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)