---
title: 选择调试引擎实施策略 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debug engines, implementation strategies
ms.assetid: 90458fdd-2d34-4f10-82dc-6d8f31b66d8b
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8a9e449fddad18c3ff0e95786ab852745407e6a1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471698"
---
# <a name="choosing-a-debug-engine-implementation-strategy"></a>选择调试引擎实施策略
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[选择调试引擎实现策略](https://docs.microsoft.com/visualstudio/extensibility/debugger/choosing-a-debug-engine-implementation-strategy)。  
  
使用运行时体系结构来确定您的调试引擎 (DE) 实施策略。 调试引擎可能会创建处理程序以进行调试，进程为 Visual Studio 会话调试管理器 (SDM) 或到这两个文件的进程外。 以下指导应帮助这些三个策略之间进行选择。  
  
## <a name="guidelines"></a>准则  
 虽然可以为 DE 为进程外到 SDM 和程序都要进行调试，没有通常无需执行此操作。 跨进程边界的调用是相对较慢。  
  
 调试引擎已提供 Win32 本机运行时环境和公共语言运行时环境。 如果您必须为两种环境替换 DE，您必须创建在进程 DE SDM。  
  
 否则，可以选择创建 DE 到 SDM 进程内或进程进行调试的程序。 请务必要考虑 DE，表达式计算器是否需要对程序符号存储区中，频繁访问以及是否在符号存储区可以加载到内存中以便快速访问。 此外请考虑以下情况：  
  
-   如果不是表达式计算器和符号存储区之间的多个调用或符号存储区可以读取到 SDM 内存空间，创建 DE 进程内运行到 SDM。 它将附加到你的程序时，您必须返回到 SDM 调试引擎的 CLSID。 SDM 使用此 CLSID 来创建 DE 的进程内实例。  
  
-   如果 DE 必须调用程序访问符号存储区，创建包含此程序中进程 DE。 在这种情况下，该程序创建 DE 的实例。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 调试器可扩展性](../../extensibility/debugger/visual-studio-debugger-extensibility.md)

