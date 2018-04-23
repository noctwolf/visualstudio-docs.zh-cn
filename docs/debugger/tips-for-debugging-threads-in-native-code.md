---
title: 调试本机代码中的线程的提示 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: c98f6bb1a738111d32b26c5b923abe41367e621e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="tips-for-debugging-threads-in-native-code"></a>调试本机代码中的线程时的提示
下面是在调试本机代码中的线程时可以使用的一些提示：  
  
-   通过键入来查看线程信息块的内容`@TIB`中**监视**窗口或**快速监视**对话框。  
  
-   你可以通过输入查看当前线程的最后一个错误代码`@Err`中**监视**窗口或**快速监视**对话框。  
  
-   可以使用 C 运行库 (CRT) 函数来调试多线程应用程序。 有关详细信息，请参阅 [_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg)。  
  
## <a name="see-also"></a>请参阅  
 [调试多线程应用程序](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [调试本机代码](../debugger/debugging-native-code.md)