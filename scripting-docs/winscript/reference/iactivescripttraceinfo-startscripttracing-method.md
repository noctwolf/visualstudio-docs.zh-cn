---
title: 'Iactivescripttraceinfo:: Startscripttracing 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 90fac5ed-ce15-49b7-a6f1-605ede6f34e2
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 824d60ef0f17012524f9d0150a90ccd9efcfb3a9
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150954"
---
# <a name="iactivescripttraceinfostartscripttracing-method"></a>IActiveScriptTraceInfo::StartScriptTracing 方法
启动脚本跟踪。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT StartScriptTracing(     [in] IActiveScriptSiteTraceInfo * pSiteTraceInfo,     [in] GUID guidContextID );   
```  
  
#### <a name="parameters"></a>参数  
 `pSiteTraceInfo`  
 指向主机的 IActiveScriptSiteTraceInfo 的指针。  
  
 `guidContextId`  
 上下文的 GUID。  
  
## <a name="return-value"></a>返回值  
 此方法可能的返回值如下所示：  
  
1.  则为 S_OK:成功。  
  
2.  E_POINTER:`pSiteTraceInfo`是 NULL 指针。  
  
3.  E_NOTIMPL:未实现。