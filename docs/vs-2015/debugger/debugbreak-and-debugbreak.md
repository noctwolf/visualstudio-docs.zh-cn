---
title: DebugBreak 和 __debugbreak |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DebugBreak
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], DebugBreak function
- DebugBreak function
- breakpoints, DebugBreak function
ms.assetid: 9787c795-df94-4f48-bc8d-3bf899b67421
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 005490038b293dbb644ec99ca2fbeaa77c0eb2c9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483274"
---
# <a name="debugbreak-and-debugbreak"></a>DebugBreak 和 __debugbreak
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[DebugBreak 和 __debugbreak](https://docs.microsoft.com/visualstudio/debugger/debugbreak-and-debugbreak)。  
  
您可以调用 DebugBreak Win32 函数或[__debugbreak](http://msdn.microsoft.com/library/1d1e1c0c-891a-4613-ae4b-d790094ba830)内部随时在代码中。 `DebugBreak` 和 `__debugbreak` 具有与在该位置设置断点相同的效果。  
  
 由于 `DebugBreak` 是对系统函数的调用，因此必须安装系统调试符号以确保中断后显示正确的调用堆栈信息。 否则，调试器可能在显示一帧调用堆栈信息后就停止显示。 如果使用 `__debugbreak`，则不需要符号。  
  
## <a name="see-also"></a>请参阅  
 [编译器内部函数](http://msdn.microsoft.com/library/48bb9929-7d78-4fd8-a092-ae3c9f971858)   
 [调试器安全](../debugger/debugger-security.md)   
 [调试本机代码](../debugger/debugging-native-code.md)   
 [指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)



