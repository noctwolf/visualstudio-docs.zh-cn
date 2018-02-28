---
title: "可以在哪里查阅 Win32 错误代码？ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.errors
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f48f3fbff8f7f18fa745df7ac9571c69038651e6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="where-can-i-look-up-win32-error-codes"></a>可以在哪里查阅 Win32 错误代码？
默认系统安装的 INCLUDE 目录中的 WINERROR.H 包含 Win32 API 函数的错误代码定义。  
  
 可以通过键入中的代码来查找错误代码**监视**窗口或**快速监视**对话框。 例如:  
  
```  
0x80000004,hr  
```  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题](../debugger/debugging-native-code-faqs.md)   
 [调试本机代码](../debugger/debugging-native-code.md)