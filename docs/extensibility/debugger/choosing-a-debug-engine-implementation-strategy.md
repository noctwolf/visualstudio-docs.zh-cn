---
title: 选择调试引擎实现策略 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, implementation strategies
ms.assetid: 90458fdd-2d34-4f10-82dc-6d8f31b66d8b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3c3715bac00b25cd2080a1162c8e2ce8cb33e63a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31098064"
---
# <a name="choosing-a-debug-engine-implementation-strategy"></a>选择调试引擎实现策略
使用运行时体系结构来确定你的调试引擎 (DE) 实现策略。 调试引擎可能会创建进程到程序要调试进程为 Visual Studio 会话调试管理器 (SDM) 或到这两个进程外。 以下准则应帮助这些三个策略之间进行选择。  
  
## <a name="guidelines"></a>准则  
 尽管很可能要进程外 DE SDM 和程序以进行调试，则通常无若要这样做。 跨进程边界的调用是相对较慢。  
  
 调试引擎已提供为 Win32 本机运行时环境和公共语言运行时环境。 如果您必须为这些环境之一替换 DE，必须通过 SDM 创建 DE 进程内。  
  
 否则，你可以选择创建 DE 到 SDM 进程内或进程到要调试程序。 请务必考虑 DE 表达式计算器是否需要频繁访问程序符号存储区，并且是否可以将符号存储区加载到内存中进行快速访问。 此外考虑以下方面：  
  
-   如果不存在表达式计算器和符号存储区，之间的多个调用或符号存储区可以读取到 SDM 内存空间，创建 DE 进程内运行到 SDM。 它会将附加到你的程序时，您必须返回到 SDM 的调试引擎的 CLSID。 SDM 使用此 CLSID 来创建的 DE 进程内实例。  
  
-   如果 DE 必须调用程序访问符号存储区，创建 DE 进程内运行的程序。 在这种情况下，程序创建 DE 的实例。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Studio 调试器可扩展性](../../extensibility/debugger/visual-studio-debugger-extensibility.md)