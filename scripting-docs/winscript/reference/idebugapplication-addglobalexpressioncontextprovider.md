---
title: IDebugApplication::AddGlobalExpressionContextProvider | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.AddGlobalExpressionContextProvider
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::AddGlobalExpressionContextProvider
ms.assetid: 35db7124-6970-4e45-8f00-ecdf21e9f5cb
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 278811ae7c7f853396efb5f41a92a5350176943a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144935"
---
# <a name="idebugapplicationaddglobalexpressioncontextprovider"></a>IDebugApplication::AddGlobalExpressionContextProvider
将全局表达式上下文提供程序添加到此应用程序。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT AddGlobalExpressionContextProvider(  
   IProvideExpressionContexts*  pdsfs,  
   DWORD_PTR*                   pdwCookie  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdsfs`  
 [in]要添加到此应用程序的全局上下文提供程序。  
  
 `pdwCookie`  
 [out]一个用于从应用程序中删除此全局表达式上下文提供程序的 cookie。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法将全局表达式上下文提供程序添加到此应用程序。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)   
 [IDebugApplication::RemoveGlobalExpressionContextProvider](../../winscript/reference/idebugapplication-removeglobalexpressioncontextprovider.md)