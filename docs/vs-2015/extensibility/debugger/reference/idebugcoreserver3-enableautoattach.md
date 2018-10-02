---
title: IDebugCoreServer3::EnableAutoAttach |Microsoft Docs
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
- IDebugCoreServer3::EnableAutoAttach
helpviewer_keywords:
- IDebugCoreServer3::EnableAutoAttach
ms.assetid: 06aa633b-263b-4e08-8844-9a52d5120b94
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4b5c420a03fd69d767331f356eb4353d52630376
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478546"
---
# <a name="idebugcoreserver3enableautoattach"></a>IDebugCoreServer3::EnableAutoAttach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugCoreServer3::EnableAutoAttach](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcoreserver3-enableautoattach)。  
  
使指定的调试引擎自动附加。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT EnableAutoAttach(  
   GUID*     rgguidSpecificEngines,  
   DWORD     celtSpecificEngines,  
   LPCOLESTR pszStartPageUrl,  
   BSTR*     pbstrSessionId  
);  
```  
  
```csharp  
int EnableAutoAttach(  
   Guid[]     rgguidSpecificEngines,  
   uint       celtSpecificEngines,  
   string     pszStartPageUrl,  
   out string pbstrSessionId  
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

