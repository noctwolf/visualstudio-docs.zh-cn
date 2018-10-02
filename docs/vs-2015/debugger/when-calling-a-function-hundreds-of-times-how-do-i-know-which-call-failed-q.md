---
title: 当一个函数被调用数百次时，如何确定哪次调用失败了？ | Microsoft Docs
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
- vs.debug.functions
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- conditional breakpoints
- errors [debugger], function calls
- breakpoints, troubleshooting
- errors [debugger], finding which function call failed
- failures
- location breakpoint call failures
- errors [Visual Studio], function calls
- hit counts
- function calls, failure
- functions [debugger]
- Skip Count
ms.assetid: 66cfac86-f5be-4d3a-9329-d44cd74bc586
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2655205c3e0c34d1063ce54793f49330ab7ccc2d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477071"
---
# <a name="when-calling-a-function-hundreds-of-times-how-do-i-know-which-call-failed"></a>当一个函数被调用数百次时，如何确定哪次调用失败了？
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[当被调用函数数百次，我如何确定失败的调用？](https://docs.microsoft.com/visualstudio/debugger/when-calling-a-function-hundreds-of-times-how-do-i-know-which-call-failed-q)。  
  
问题描述  
 程序在调用某函数（如 `CnvtV`）时失败。 失败以前该程序可能已调用了该函数数百次。 如果我在 `CnvtV` 上设置一个位置断点，程序在每次调用该函数时都停止，而我不希望这样。 我不知道什么条件导致调用失败，所以无法设置条件断点。 我该怎么办？  
  
## <a name="solution"></a>解决方案  
 可以在函数上设置断点**命中次数**字段为大到永远不会无法达到的值。 在这种情况下，由于您确信函数`CnvtV`被调用了数百次，您可以设置**命中计数**为 1000年或更多。 然后运行程序，等待调用失败。 程序失败后，打开“断点”窗口并查看断点列表。 将显示您在 `CnvtV` 上设置的断点，其后跟着命中次数和剩余迭代次数：  
  
```  
CnvtV(int) (no condition) when hit count is equal to 1000 (currently 101)  
```  
  
 现在您知道函数在第 101 次调用时失败。 如果重置断点，将命中次数设置为 101，然后再次运行程序，程序将在导致 `CnvtV` 调用失败的位置停止所有该调用。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)   
 [设置断点](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [调试本机代码](../debugger/debugging-native-code.md)



