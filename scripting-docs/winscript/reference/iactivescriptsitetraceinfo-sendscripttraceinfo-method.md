---
title: 'Iactivescriptsitetraceinfo:: Sendscripttraceinfo 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0419e4c5-eb7c-45a3-b6dc-1a5e157d95f9
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0f08a5cb0e7bd297dede85190ac694185e2fd795
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091619"
---
# <a name="iactivescriptsitetraceinfosendscripttraceinfo-method"></a>IActiveScriptSiteTraceInfo::SendScriptTraceInfo 方法
将发送跟踪信息，包括事件类型、 上下文和脚本语句。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SendScriptTraceInfo(     [in] SCRIPTTRACEINFO stiEventType,     [in] GUID guidContextID,     [in] DWORD dwScriptContextCookie,     [in] LONG lScriptStatementStart,     [in] LONG lScriptStatementEnd,     [in] DWORD64 dwReserved );   
```  
  
#### <a name="parameters"></a>参数  
 `stiEventType`  
 事件类型。  
  
 `guidContextId`  
 上下文的 GUID。  
  
 `dwScriptContextCookie`  
 上下文的 cookie。  
  
 `lScriptStatementStart`  
 脚本语句的起始位置。  
  
 `lScriptStatementEnd`  
 脚本语句的末尾的位置。  
  
 `dwReserved`  
 保留。