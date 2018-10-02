---
title: 如何在逐句通过程序时保持焦点？ | Microsoft Docs
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
- vs.debug.stepping
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], stepping
- focus, keeping
- stepping, focus
- windows, troubleshooting activation
ms.assetid: 11a30580-3a1a-4be8-a241-0abdc758302e
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7598e25a6e436702b88b7e10d6cde7968a8cc61d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477323"
---
# <a name="how-can-i-keep-focus-when-stepping-through-my-program"></a>如何在逐句通过程序时保持焦点？
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何保持焦点时单步执行通过我程序？](https://docs.microsoft.com/visualstudio/debugger/how-can-i-keep-focus-when-stepping-through-my-program-q)。  
  
描述  
 我的程序存在窗口激活问题。 用调试器逐句通过程序时，因为程序不断失去焦点，所以妨碍了再现问题。 是否有方法可以避免该问题？  
  
## <a name="solution"></a>解决方案  
 如果有另一台计算机，请使用远程调试。 可以在远程计算机上运行您的程序，而在主机上运行调试器。 有关详细信息，请参阅[如何： 选择远程计算机](http://msdn.microsoft.com/en-us/4332ba8e-2f0b-4f62-b96a-e762b9f3c3ba)。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)   
 [将附加到正在运行的进程](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [调试本机代码](../debugger/debugging-native-code.md)



