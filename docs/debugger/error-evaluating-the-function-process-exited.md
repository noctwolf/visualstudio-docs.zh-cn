---
title: 错误： 目标进程已退出，代码&#39;代码&#39;时对函数求值&#39;函数&#39;|Microsoft 文档
ms.custom: ''
ms.date: 4/06/2018
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.process_exit_during_func_eval
ms.technology: vs-ide-debug
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d5e9221ccf162180a89cc88b1ceebcf55be39eef
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31922506"
---
# <a name="error-the-target-process-exited-with-code-39code39-while-evaluating-the-function-39function39"></a>错误： 目标进程已退出，代码&#39;代码&#39;时对函数求值&#39;函数&#39;

完整消息文本： 目标进程退出，代码为 code 函数 function 求值时。

若要更加轻松地检查.NET 对象的状态，调试器将自动强制执行调试的进程来运行其他代码 (通常是属性 getter 方法和`ToString`函数)。 在大多数情况下，这些函数已成功完成，或引发可由调试器捕获的异常。 但是，在某些情况下，因为它们跨内核边界，需要用户消息泵处理，或者是不可恢复，则不能捕获在其中的异常。 作为结果，属性 getter 或执行代码的 ToString 方法的显式终止进程 (例如，调用`ExitProcess()`) 或引发未经处理的异常，无法捕获 (例如， `StackOverflowException`) 将终止调试的进程并结束调试会话。 如果遇到此错误消息，你将会发生这种情况。
 
此问题的一个常见原因是，当调试器将计算调用其自身的属性，这可能会导致堆栈溢出异常。 无法恢复堆栈溢出异常，并且目标进程将终止。
 
## <a name="to-correct-this-error"></a>更正此错误
 
没有与此问题的两个可能的解决方案。
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>解决方案 #1： 防止调试器调用属性 getter 或 ToString 方法 

错误消息将通知调试器尝试调用的函数的名称。 函数的名称，你可以尝试重新评估该函数从**即时**窗口调试评估。 调试时可能会从评估**即时**窗口，因为与隐式评估与不同**自动/局部变量/监视**windows，调试器将在未经处理的异常处中断。

如果可以修改此函数，则你可以调用属性 getter 阻止调试器或`ToString`方法。 请尝试以下方法之一：
 
* 将方法更改为某些其他类型的属性 getter 除了代码或 ToString 方法和问题将会消失。
    -或-
* (有关`ToString`) 定义`DebuggerDisplay`属性的类型以及你可以让调试器以外评估内容`ToString`。
    -或-
* （适用于属性 getter)Put`[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]`的属性上的属性。 这很有用，如果你的需要保持属性的 API 兼容性原因，一个方法，但它确实应该为一种方法。

如果你不能修改此方法，你可以在备用指令处中断目标进程，然后重试评估。
 
### <a name="solution-2-disable-all-implicit-evaluation"></a>解决方案 2： 禁用所有隐式计算
 
如果以前的解决方案不解决此问题，请转到**工具** > **选项**，并取消选中设置**调试** >  **常规** > **启用属性求值和其他隐式函数调用**。 这将禁用大多数隐式函数计算，并应该解决此问题。



  
