---
title: IActiveScriptWinRTErrorDebug 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptWinRTErrorDebug Interface
ms.assetid: 58b45096-633f-479f-95c4-8eae7376d3a1
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2355b9aa38abbed2ca66964a07bb47082eb76c32
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346496"
---
# <a name="iactivescriptwinrterrordebug-interface"></a>IActiveScriptWinRTErrorDebug 接口
由 JavaScript 引擎提供扩展的 Windows 运行时错误信息从实现[BREAKREASON 枚举](../../winscript/reference/breakreason-enumeration.md)事件。 您可以执行 QueryInterface 以从中获取此[IActiveScriptError](../../winscript/reference/iactivescripterror.md)对象。  
  
> [!IMPORTANT]
>  此接口由 PDM v11.0 和更高版本实现。 在 activdbg100.h 中发现。  
  
## <a name="methods"></a>方法  
 `IActiveScriptWinRTErrorDebug` 接口公开以下方法。  
  
|方法|描述|  
|------------|-----------------|  
|[IActiveScriptWinRTErrorDebug::GetCapabilitySid](../../winscript/reference/iactivescriptwinrterrordebug-getcapabilitysid.md)|如果可用，则返回 Windows 运行时错误的功能的 SID。|  
|[IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference](../../winscript/reference/iactivescriptwinrterrordebug-getrestrictederrorreference.md)|如果可用，则返回 Windows 运行时限制错误引用字符串。|  
|[IActiveScriptWinRTErrorDebug::GetRestrictedErrorString](../../winscript/reference/iactivescriptwinrterrordebug-getrestrictederrorstring.md)|如果可用，则返回 Windows 运行时限制错误字符串。|