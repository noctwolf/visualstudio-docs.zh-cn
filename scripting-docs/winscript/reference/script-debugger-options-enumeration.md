---
title: SCRIPT_DEBUGGER_OPTIONS 枚举 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SCRIPT_DEBUGGER_OPTIONS Enumeration
ms.assetid: aef41ec0-6f65-48e8-a69e-44b4e4fb929f
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 25f74902e2fea451ae5ddaf75d215c3a6c70b050
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155037"
---
# <a name="scriptdebuggeroptions-enumeration"></a>SCRIPT_DEBUGGER_OPTIONS 枚举
指示一系列选项和/或将应用于附加调试器的功能。 在中使用[IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)和[IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)  
  
> [!IMPORTANT]
>  这些常量由 PDM 10.0 版及更高版本实现。 在 activdbg100.h 中发现。  
  
## <a name="syntax"></a>语法  
  
```cpp
typedef SCRIPT_DEBUGGER_OPTIONS  
```  
  
## <a name="members"></a>成员  
  
|成员|“值”|描述|  
|------------|-----------|-----------------|  
|SDO_NONE|0x00000000|未设置选项。|  
|SDO_ENABLE_FIRST_CHANCE_EXCEPTIONS|0x00000001|指示脚本运行时应引发将引发异常时，会发生 BREAKREASON_ERROR 事件。 此选项可能设置由调试器，或由用户代码通过设置`Debug.enableFirstChanceExceptions(<true&#124;false>)`。|  
|SDO_ENABLE_WEB_WORKER_SUPPORT|0x00000002|指示连接的调试器支持 web 辅助进程。|  
  
## <a name="see-also"></a>请参阅  
 [活动脚本调试器常量、枚举和结构](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)