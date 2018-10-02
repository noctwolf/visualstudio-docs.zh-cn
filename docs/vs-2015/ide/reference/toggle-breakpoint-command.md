---
title: “切换断点”命令 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.togglebreakpoint
helpviewer_keywords:
- ToggleBreakpoint command
- Debug.ToggleBreakPoint command
- Toggle Breakpoint command
ms.assetid: d50dfadb-ce79-4d5e-9c09-1cfddd57876d
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c7dd3bd7a4d42b8135aed034464223af53091f87
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468917"
---
# <a name="toggle-breakpoint-command"></a>“切换断点”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[切换断点命令](https://docs.microsoft.com/visualstudio/ide/reference/toggle-breakpoint-command)。  
  
  
在文件中的当前位置，根据其当前状态打开或关闭断点。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.ToggleBreakpoint [text]  
```  
  
## <a name="arguments"></a>自变量  
 `text`  
 可选。 如果已指定文本，该行将标记为已命名断点。 否则，该行标记为未命名断点，其结果与按下 F9 时的效果类似。  
  
## <a name="example"></a>示例  
 以下示例切换当前断点。  
  
```  
>Debug.ToggleBreakpoint  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)



