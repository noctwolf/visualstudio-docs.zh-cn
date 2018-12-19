---
title: 逐句通过我的应用程序时保持焦点 |Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.stepping
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], stepping
- focus, keeping
- stepping, focus
- windows, troubleshooting activation
ms.assetid: 11a30580-3a1a-4be8-a241-0abdc758302e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d140617aed2e6d5310587ec9388b107404398a95
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53064506"
---
# <a name="how-can-i-keep-focus-when-stepping-through-my-app"></a>如何在逐句通过我的应用程序时保持焦点？
## <a name="description"></a>说明  
 我的程序存在窗口激活问题。 用调试器逐句通过程序时，因为程序不断失去焦点，所以妨碍了再现问题。 是否有方法可以避免该问题？  
  
## <a name="solution"></a>解决方案  
 如果有另一台计算机，请使用远程调试。 可以在远程计算机上运行您的程序，而在主机上运行调试器。 有关更多信息，请参见[如何：选择远程计算机](/previous-versions/visualstudio/visual-studio-2010/w8wtw2f3(v=vs.100))。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)   
 [附加到正在运行的进程](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [调试本机代码](../debugger/debugging-native-code.md)