---
title: 异常后继续执行 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- managed exceptions, continuing execution after
- exceptions, continuing execution after
- debugger, exceptions
- managed code, exception handling
- exception handling, continuing execution after
- execution, continuing after an exception
- program execution
- threading [Visual Studio], continuing execution after exceptions
- Exceptions dialog box
- programs, executing
ms.assetid: 6fe97aac-2131-4615-bd92-d3afee741558
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f9e99a29c097bdf5e23bdb8f4955cd1ccc7ec19e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49230121"
---
# <a name="continuing-execution-after-an-exception"></a>在出现异常之后继续执行
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

当调试器因出现异常而中断执行时，会显示一个对话框。 对于 Visual Basic 或 C# 中，您将看到[异常助手](http://msdn.microsoft.com/library/992892ac-9d52-44cc-bf09-b44bfc5befeb)对话框中的，默认情况下。 对于 c + +，您将看到较早**异常**对话框。 如果您使用的 Visual Basic 或 C#，但已禁用**异常助手**中**选项**对话框中，您将看到**异常**对话框。  
  
 当**异常助手**或**异常**对话框随即出现，你可以尝试修复导致异常的问题。  
  
## <a name="managed-code"></a>托管代码  
 在托管代码中，你可以在出现未经处理的异常后在同一线程内继续执行。 **异常助手**将回退到引发异常的点的调用堆栈。  
  
## <a name="native-code"></a>本机代码  
 在本机 C/C++ 中，您有两个选项：  
  
-   可以单击**中断**并尝试修复此问题。 当你处于中断模式下时，可以通过右键单击在帧上展开调用堆栈**调用堆栈**窗口并选择**展开到此帧**快捷菜单上。 当你继续调试，请**异常**对话框将再次显示未能修复问题。 否则为**异常**对话框不会再次出现。  
  
-   可以单击**继续**不尝试解决该问题的情况下继续执行。 **异常**对话框再次出现。  
  
## <a name="mixed-code"></a>混合代码  
 如果在调试本机和托管混合的代码时遇到未经处理的异常，则操作系统约束将阻止调用堆栈展开。 如果尝试使用快捷菜单来展开调用堆栈，则会出现一个错误消息，告诉你在混合代码调试期间，调试器无法在异常未得到处理的情况下展开调用堆栈。  
  
## <a name="see-also"></a>请参阅  
 [管理调试器的异常](../debugger/managing-exceptions-with-the-debugger.md)





