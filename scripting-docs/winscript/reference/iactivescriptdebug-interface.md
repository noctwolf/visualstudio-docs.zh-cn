---
title: IActiveScriptDebug 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptDebug interface
ms.assetid: e3e28cba-ee08-4a52-973a-b74be488c348
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0e21f4c99da886bc4907acf8b0934e1b46d57689
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942083"
---
# <a name="iactivescriptdebug-interface"></a>IActiveScriptDebug 接口
由脚本引擎实现该支持调试。 通常情况下，实现的对象`IActiveScriptDebug`接口还实现`IActiveScript`接口。 如果是这样，调用`IActiveScript::QueryInterface`方法来获取`IActiveScriptDebug`接口。  
  
 `IActiveScriptDebug`接口提供了有关方式：  
  
- 若要继续使用文档管理的智能主机。  
  
- 进程调试管理器来同步多个脚本引擎的调试。  
  
  除了继承的方法之外`IUnknown`，则`IActiveScriptDebug`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IActiveScriptDebug::GetScriptTextAttributes](../../winscript/reference/iactivescriptdebug-getscripttextattributes.md)|返回脚本文本的任意块的文本属性。|  
|[IActiveScriptDebug::GetScriptletTextAttributes](../../winscript/reference/iactivescriptdebug-getscriptlettextattributes.md)|返回任意 scriptlet 的文本属性。|  
|[IActiveScriptDebug::EnumCodeContextsOfPosition](../../winscript/reference/iactivescriptdebug-enumcodecontextsofposition.md)|委托给`IDebugDocumentContext::EnumCodeContexts`。|