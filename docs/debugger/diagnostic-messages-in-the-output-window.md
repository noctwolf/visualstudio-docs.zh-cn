---
title: 将诊断消息发送到输出窗口 |Microsoft Docs
ms.custom: ''
ms.date: 04/25/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- diagnostic messages [C#]
- System.Diagnostics.Debug class, Output window
- messages, diagnostic
- Debug.Print replacements
- diagnosis
- Output window, diagnostic messages
- System.Diagnostics.Trace class, Output window
- Trace class, diagnostic messages
- diagnostics
- debugger, Output window
- debugging [Visual Studio], diagnostic messages in Output window
- Debug class
ms.assetid: 386e9524-be17-4573-83fb-4f7c5cae0be0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 27cec31b775ba5f8d201c81cbd65f5b161353986
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39252292"
---
# <a name="send-diagnostic-messages-to-the-output-window"></a>将诊断消息发送到输出窗口
可以将运行时消息写入**输出**窗口中使用<xref:System.Diagnostics.Debug>类或<xref:System.Diagnostics.Trace>类，该类是一部分的<xref:System.Diagnostics>类库。 使用<xref:System.Diagnostics.Debug>类只在输出，则如果*调试*程序的版本。 使用<xref:System.Diagnostics.Trace>类，如果你想在这种输出*调试*并*发行*版本。  
  
## <a name="output-methods"></a>输出方法  
 <xref:System.Diagnostics.Trace> 和 <xref:System.Diagnostics.Debug> 类提供下列输出方法：  
  
-   在不中断执行情况下输出信息的各种 `Write` 方法。 这些方法取代了在 Visual Basic 早期版本中使用的 `Debug.Print` 方法。  
  
-   <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 和 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> 方法，如果指定的条件失败，这些方法将中断执行并输出信息。 默认情况下，`Assert` 方法显示对话框中的信息。 有关详细信息，请参阅[托管代码中的断言](../debugger/assertions-in-managed-code.md)。  
  
-   <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> 和 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> 方法，它们总是中断执行并输出信息。 默认情况下，`Fail` 方法在对话框中显示信息。  
  
 扩展程序从应用程序中，除了**输出**窗口可以显示下列信息：  
  
-   调试器已经加载或卸载的模块。  
  
-   引发的异常。  
  
-   退出的进程。  
  
-   退出的线程。  
  
## <a name="see-also"></a>请参阅  
 [调试器安全](../debugger/debugger-security.md)   
 [“输出”窗口](../ide/reference/output-window.md)   
 [跟踪应用程序和在应用程序中插入检测点](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)  
 [C#、F#、和 Visual Basic 项目类型](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [调试托管代码](../debugger/debugging-managed-code.md)
