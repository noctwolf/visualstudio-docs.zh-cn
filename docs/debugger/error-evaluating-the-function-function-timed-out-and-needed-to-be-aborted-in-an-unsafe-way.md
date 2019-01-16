---
title: 错误： 对函数求值&#39;函数&#39;超时，需要以不安全的方式中止 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.unsafe_func_eval_abort
ms.technology: vs-ide-debug
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f36e56b2870d5f099a3b8ed95265fe7e2d688ff
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49934439"
---
# <a name="error-evaluating-the-function-39function39-timed-out-and-needed-to-be-aborted-in-an-unsafe-way"></a>错误： 对函数求值&#39;函数&#39;超时，需要以不安全的方式中止

完整的消息文本： 评估函数 function 超时，需要以不安全的方式中止。 这可能会损坏目标进程。 

若要更加轻松地检查.NET 对象的状态，调试器会自动强制调试的进程来运行其他代码 （通常是属性 getter 方法和 ToString 函数）。 在大多数的所有情况下，这些函数快速完成，并使调试更加容易。 但是，调试器不会在沙盒中运行应用程序。 因此，属性 getter 或调入挂起的本机函数的 ToString 方法可能会导致长的超时可能无法恢复。 如果遇到此错误消息，此问题发生。
 
对于此问题的一个常见原因是当调试器将计算属性，则它只允许检查要执行的线程。 因此如果该属性正在等待其他线程来运行在调试应用程序，并且它正在等待.NET 运行时不能中断的方式，将会发生此问题。
 
## <a name="to-correct-this-error"></a>更正此错误
 
有三个可能的解决方案，此问题。
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>解决方法 #1： 防止调试器调用 getter 的属性或 ToString 方法
 
错误消息将告知调试器尝试调用的函数的名称。 如果可以修改此函数，您可以防止调试器调用属性 getter 或 ToString 方法。 请尝试以下方法之一：
 
* 将方法更改为其他类型的代码属性 getter 或 ToString 方法和问题将会消失。
    或
* （适用于 ToString)在类型上定义 DebuggerDisplay 特性，您可以评估 ToString 以外的调试器。
    或
* （适用于属性 getter)放置`[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]`属性上的属性。 这会很有用，如果有需要保留有关 API 兼容性原因，属性的方法，但它确实应该有方法。
 
### <a name="solution-2-have-the-target-code-ask-the-debugger-to-abort-the-evaluation"></a>解决方案 #2：通过目标代码要求调试器中止评估
 
错误消息将告知调试器尝试调用的函数的名称。 如果属性 getter 或 ToString 方法有时无法正确运行，尤其是在情况下，此问题时，代码需要另一个线程来运行代码，然后实现函数可以调用`System.Diagnostics.Debugger.NotifyOfCrossThreadDependency`询问调试器中止该函数求值。 使用此解决方案，则仍可以显式评估了这些函数，但默认行为是执行停止 NotifyOfCrossThreadDependency 调用发生时。
 
### <a name="solution-3-disable-all-implicit-evaluation"></a>解决方案 3： 禁用所有隐式计算
 
如果先前的解决方案未解决此问题，请转到*工具* > *选项*，并取消选中该设置*调试* >  *常规* > *启用属性求值和其他隐式函数调用*。 这将会禁用大多数隐式函数求值，然后应解决的问题。



  
