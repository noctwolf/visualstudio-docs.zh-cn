---
title: IDebugEngine2::SetLocale |Microsoft Docs
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
- IDebugEngine2::SetLocale
helpviewer_keywords:
- IDebugEngine2::SetLocale
ms.assetid: cd0d2cf1-2aac-43da-a830-4bb3d696c219
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4743f536846cc02eec6e4ea598506c448a8ea96c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481387"
---
# <a name="idebugengine2setlocale"></a>IDebugEngine2::SetLocale
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugEngine2::SetLocale](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugengine2-setlocale)。  
  
设置调试引擎 (DE) 的区域设置。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT SetLocale(   
   WORD wLangID  
);  
```  
  
```csharp  
int SetLocale(   
   ushort wLangID  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wLangID`  
 [in]指定的语言区域设置。 例如，1033 为英语的。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 会话调试管理器 (SDM) 传播 IDE 的区域设置，以便正确本地化字符串 DE 返回通过调用此方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)

