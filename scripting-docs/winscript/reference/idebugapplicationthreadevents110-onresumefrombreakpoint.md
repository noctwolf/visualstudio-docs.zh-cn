---
title: IDebugApplicationThreadEvents110::OnResumeFromBreakPoint |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThreadEvents110::OnResumeFromBreakPoint
ms.assetid: 4c97b9a3-fced-487e-a81c-e3f8f2cb7927
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b681a9c89a2b7d48864e7ed3fc48460c64d2878
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160597"
---
# <a name="idebugapplicationthreadevents110onresumefrombreakpoint"></a>IDebugApplicationThreadEvents110::OnResumeFromBreakPoint
该线程从断点恢复，并将再一次处于活动状态。  
  
> [!IMPORTANT]
>  [IDebugApplicationThreadEvents110 接口](../../winscript/reference/idebugapplicationthreadevents110-interface.md)是实现由 PDM v11.0 和更高版本。 在 activdbg100.h 中发现。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT OnResumeFromBreakPoint( void );  
```  
  
#### <a name="parameters"></a>参数  
 此方法没有任何参数。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplicationThreadEvents110 接口](../../winscript/reference/idebugapplicationthreadevents110-interface.md)