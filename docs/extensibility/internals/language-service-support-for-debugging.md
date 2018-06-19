---
title: 语言服务支持用于调试 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 59c044f6ffc3f2cdf0749f0192f4b8fa458b00cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128646"
---
# <a name="language-service-support-for-debugging"></a>用于调试的语言服务支持
语言服务能够提供支持通过调试器的功能<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo>接口。 这些功能包括验证断点并提供到表达式列表**自动**窗口。  
  
 但是，你需要调试你的语言的表达式计算器。 表达式计算器负责计算表达式在调试时生成值。 有关实现 CLR 表达式计算器的信息，请参阅：  
  
-   [CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)  
  
-   [托管的表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)  
  
## <a name="compiler-output"></a>编译器输出  
 编译器的类型决定你需要执行操作来实现对你的语言的调试。 如果你的编译器面向 Windows 操作系统，并编写.pdb 文件，您可以使用本机代码调试引擎集成到 Visual Studio 调试程序。 如果你的编译器生成 Microsoft 中间语言 (MSIL)，你可以用托管代码调试引擎，还集成到 Visual Studio 调试程序。 如果你的编译器面向专有的操作系统或不同的运行时环境，你需要编写你自己的调试引擎。  
  
 有关实现调试你的语言的详细信息，请参阅[入门](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)Visual Studio 调试 SDK 中。