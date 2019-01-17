---
title: IActiveScriptSiteDebugEx 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteDebugEx Interface
ms.assetid: 76869378-1a7b-47bd-8cd0-acc31f91d58d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c1e462630f7bf52c4ca94aa59df22616e9a335a7
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345872"
---
# <a name="iactivescriptsitedebugex-interface"></a>IActiveScriptSiteDebugEx 接口
实现此接口与`IActiveScriptSiteDebug`接口如果你正在编写需要应用程序中收到的运行时错误通知，并根据需要将附加到调试的应用程序的主机。 进程调试管理器提供了通知通过`IActiveScriptDebug`如果中实时脚本调试程序在计算机上找到。 如果没有时间就脚本调试程序是找到 PDM 提供了通知通过`IActiveScriptDebugEx`相反。  
  
 若要获取运行时错误的通知，你的主机必须处理[ActiveScriptSiteDebug::OnScriptErrorDebug](http://msdn.microsoft.com/en-us/cf7639f9-a699-4571-9f3a-82ef52c0b5f4)。 根据用户操作，您可以决定是要附加的内部调试器和返回时，还是返回 OnScriptErrorDebug 中调试器的起始`pfEnterDebugger`参数。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug](../../winscript/reference/iactivescriptsitedebugex-oncannotjitscripterrordebug.md)|通知主机有关脚本运行时错误进程调试管理器时未找到外部的实时调试器。|