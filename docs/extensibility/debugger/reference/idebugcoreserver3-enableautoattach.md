---
title: IDebugCoreServer3::EnableAutoAttach |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer3::EnableAutoAttach
helpviewer_keywords:
- IDebugCoreServer3::EnableAutoAttach
ms.assetid: 06aa633b-263b-4e08-8844-9a52d5120b94
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2477ac13218342511ac7b47bec6cf847651cfb22
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53913065"
---
# <a name="idebugcoreserver3enableautoattach"></a>IDebugCoreServer3::EnableAutoAttach
使指定的调试引擎自动附加。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnableAutoAttach(  
   GUID*     rgguidSpecificEngines,  
   DWORD     celtSpecificEngines,  
   LPCOLESTR pszStartPageUrl,  
   BSTR*     pbstrSessionId  
);  
```  
  
```csharp  
int EnableAutoAttach(  
   Guid[]     rgguidSpecificEngines,  
   uint       celtSpecificEngines,  
   string     pszStartPageUrl,  
   out string pbstrSessionId  
);  
```  
  
#### <a name="parameters"></a>参数  
 `rgguidSpecificEngines`  
 [in]Guid 的数组，每种调试引擎将标记为自动附加。  
  
 `celtSpecificEngines`  
 [in]中指定的引擎数`rgguidSpecificEngines`。  
  
 `pszStartPageUrl`  
 [in]要使用自动附加时的起始 URL。  
  
 `pbstrSessionID`  
 [out]已自动附加的会话 ID。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。 一个错误代码是`E_AUTO_ATTACH_NOT_REGISTERED`，指示尚未注册 auto-attach 类工厂。  
  
## <a name="remarks"></a>备注  
 使用指定的 URL 关联的程序启动时，指定的调试引擎自动启动和附加。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)