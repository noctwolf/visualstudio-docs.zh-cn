---
title: 如何： 重新回到这儿中断时调用 MFC 的函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.mfc
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: da15793027eb643078771d33464258fea73fec9d
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283387"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>如何：返回到在中断时调用了 MFC 的函数
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在“工具”菜单上选择“导入和导出设置”。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)。  
  
 如果您使用了**中断**命令**调试**菜单来暂停程序和最终在 MFC 中，并确认该问题会在代码中，可以使用调用堆栈窗口导航回您的函数。 有关详细信息，请参阅[如何： 使用调用堆栈窗口](../debugger/how-to-use-the-call-stack-window.md)。  
  
 有时，代码可能在消息泵中中断。 在这种情况下，调用堆栈中没有用户代码。 若要避免此问题，可以使用断点 （也许加上条件和命中的次数） 而不是**中断**命令。 有关详细信息，请参阅[断点和跟踪点](https://msdn.microsoft.com/library/fe4eedc1-71aa-4928-962f-0912c334d583)。  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>若要定位调用 MFC 的函数  
  
-   使用**调用堆栈**窗口。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)   
 [调试本机代码](../debugger/debugging-native-code.md)