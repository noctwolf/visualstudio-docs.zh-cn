---
title: 错误：目标进程已退出，代码&#39;代码&#39;对函数求值时&#39;函数&#39;|Microsoft Docs
ms.date: 4/06/2018
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.process_exit_during_func_eval
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 78580cad30447419734afd9ef8c8fbc490e516e5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53882385"
---
# <a name="error-the-target-process-exited-with-code-39code39-while-evaluating-the-function-39function39"></a>错误：目标进程已退出，代码&#39;代码&#39;对函数求值时&#39;函数&#39;

完整的消息文本：评估函数“function”时，目标进程退出并生成代码“code”

若要更加轻松地检查.NET 对象的状态，调试器会自动强制调试的进程来运行其他代码 (通常是属性 getter 方法和`ToString`函数)。 在大多数情况下，这些函数已成功完成或引发可由调试器捕获的异常。 但是，在某些情况下，因为它们跨越内核边界、 需要用户消息泵处理，或者是无法恢复的异常不能捕获在其中。 作为结果、 属性 getter 或执行代码的 ToString 方法，或者显式终止进程 (例如，调用`ExitProcess()`) 或引发未经处理的异常不能被捕获 (例如， `StackOverflowException`) 将终止调试的进程并结束调试会话。 如果遇到此错误消息，此问题发生。
 
对于此问题的一个常见原因是，当调试器将计算调用其自身的属性，这可能会导致堆栈溢出异常。 无法恢复堆栈溢出异常，目标进程将终止。
 
## <a name="to-correct-this-error"></a>更正此错误
 
有两个可能的解决方案，此问题。
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>解决方案 1防止调试器调用 getter 的属性或 ToString 方法 

错误消息将告知调试器尝试调用函数的名称。 函数的名称，则可以尝试重新计算该函数从**即时**窗口调试计算。 调试时，可能从评估**即时**窗口中，因为与隐式评估与不同**自动/局部变量/监视**windows，调试器将在未经处理的异常处中断。

如果可以修改此函数，您可以阻止调试器调用属性 getter 或`ToString`方法。 请尝试以下方法之一：
 
* 将方法更改为其他类型的代码属性 getter 或 ToString 方法和问题将会消失。
    或
* (有关`ToString`) 定义`DebuggerDisplay`属性的类型和您可以已评估的内容而不将调试器`ToString`。
    或
* （适用于属性 getter)放置`[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]`属性上的属性。 这会很有用，如果有需要保持 API 兼容性原因，一个属性的方法，但它确实应该有方法。

如果您不能修改此方法，您可以在备用的指令处中断目标进程，然后重试评估。
 
### <a name="solution-2-disable-all-implicit-evaluation"></a>解决方案 2禁用所有隐式计算
 
如果先前的解决方案未解决此问题，请转到**工具** > **选项**，并取消选中该设置**调试** >  **常规** > **启用属性求值和其他隐式函数调用**。 这将会禁用大多数隐式函数求值，然后应解决的问题。
