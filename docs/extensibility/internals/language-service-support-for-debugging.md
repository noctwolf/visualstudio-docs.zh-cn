---
title: 用于调试的语言服务支持 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b42e11974a0522b8f4a6553c5606197915617d38
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60110860"
---
# <a name="language-service-support-for-debugging"></a>用于调试的语言服务支持
语言服务可以提供可支持通过调试器功能<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo>接口。 这些功能包括验证断点并提供一系列表达式到**自动**窗口。

 但是，你需要具有要调试您的语言的表达式计算器。 表达式计算器负责评估表达式来进行调试时生成值。 有关实现 CLR 表达式计算器的信息，请参阅：

- [CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)

- [托管的表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)

## <a name="compiler-output"></a>编译器输出
 编译器的类型确定需要执行的操作实现调试你的语言。 如果您的编译器面向 Windows 操作系统，并编写一个.pdb 文件，可以使用本机代码调试引擎集成到 Visual Studio 调试程序。 如果您的编译器生成 Microsoft 中间语言 (MSIL)，可以使用托管代码调试引擎，还集成到 Visual Studio 调试程序。 如果您的编译器面向专有操作系统或不同的运行时环境，需要编写你自己的调试引擎。

 有关实现调试你的语言的详细信息，请参阅[Getting Started](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) Visual Studio 调试 SDK 中。