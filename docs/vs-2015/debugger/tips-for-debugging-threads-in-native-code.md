---
title: 调试本机代码中的线程的提示 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02343da30e4f185a5b4aa236ed9b0b3ef823c4bb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470694"
---
# <a name="tips-for-debugging-threads-in-native-code"></a>调试本机代码中的线程时的提示
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[调试本机代码中的线程的提示](https://docs.microsoft.com/visualstudio/debugger/tips-for-debugging-threads-in-native-code)。  
  
下面是在调试本机代码中的线程时可以使用的一些提示：  
  
-   可以通过键入查看线程信息块的内容`@TIB`中**观看**窗口或**快速监视**对话框。  
  
-   可以通过输入查看当前线程的最后一个错误代码`@Err`中**观看**窗口或**快速监视**对话框。  
  
-   可以使用 C 运行库 (CRT) 函数来调试多线程应用程序。 有关详细信息，请参阅 [_malloc_dbg](http://msdn.microsoft.com/library/c97eca51-140b-4461-8bd2-28965b49ecdb)。  
  
## <a name="see-also"></a>请参阅  
 [调试多线程应用程序](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [调试本机代码](../debugger/debugging-native-code.md)



