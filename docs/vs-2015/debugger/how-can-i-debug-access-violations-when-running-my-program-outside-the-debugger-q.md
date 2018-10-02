---
title: 在调试器外部运行程序时如何调试访问冲突？ | Microsoft Docs
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
- vs.debug.access
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1525061210c6ef7cdda32c6204648c3944f4b889
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469816"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>在调试器外部运行程序时如何调试访问冲突？
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何调试访问冲突时运行我程序外部调试器？](https://docs.microsoft.com/visualstudio/debugger/how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger-q)。  
  
问题描述  
 我的程序在 Visual Studio 环境中运行良好，但在 Windows 操作系统中独立运行时产生访问冲突。 如何调试该问题？  
  
## <a name="solution"></a>解决方案  
 设置[中实时调试](../debugger/just-in-time-debugging-in-visual-studio.md)选项并运行独立应用程序，直到发生访问冲突。 然后，在**访问冲突**对话框中，你可以单击**取消**启动调试器。  
  
 请参见知识库文章 Q133174“How to Locate Where a General Protection (GP) Fault Occurs”（如何定位通用性保护 (GP) 错误的发生位置）。 MSDN 库 CD 上或通过搜索可以查找知识库文章[ http://support.microsoft.com/ ](http://support.microsoft.com/)。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)   
 [调试本机代码](../debugger/debugging-native-code.md)



