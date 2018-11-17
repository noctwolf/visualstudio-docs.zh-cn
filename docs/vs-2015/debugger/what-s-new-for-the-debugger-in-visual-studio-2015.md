---
title: 什么是 Visual Studio 2015 中调试器的新增功能 |Microsoft Docs
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
helpviewer_keywords:
- debugger, what's new
- what's new [debugger]
- debugging [Visual Studio], what's new
- what's new [Visual Studio], debugging
ms.assetid: 2aed9caa-2384-4e49-8595-82d8b06cf271
caps.latest.revision: 86
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 859233c1c79360f28e306dc0fca7df574cb39ccf
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51774882"
---
# <a name="whats-new-for-the-debugger-in-visual-studio-2015"></a>Visual Studio 2015 中调试器的新增功能
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

有关 Visual Studio 2015 Update 1 调试和诊断中的所有新增功能的信息，请参阅 [Visual Studio 2015 Update 1 发行说明](https://www.visualstudio.com/news/vs2015-update1-vs#debug)。  
  
 有关 Visual Studio 2015 RTM 调试和诊断中的所有新增功能的信息，请参阅 [Visual Studio 2015 发行说明](https://www.visualstudio.com/news/vs2015-vs#debug)。  
  
## <a name="visual-studio-2015-update-1-changes"></a>Visual Studio 2015 Update 1 更改  
 C++“编辑并继续”支持更多功能。 有关详细信息，请参阅[编辑并继续 （Visual c + +）](../debugger/edit-and-continue-visual-cpp.md)。  
  
 为调试 Visual C++ 访问冲突，将由新建异常对话框指定导致异常的指针。 有关详细信息，请参阅 [How Can I Debug an Access Violation?](../debugger/how-can-i-debug-an-access-violation-q.md) 和 [Visual Studio 2015 Update 1 中为调试 C++ 访问冲突而进行的改进](http://blogs.msdn.com/b/visualstudioalm/archive/2015/10/29/improvement-to-debugging-c-access-violations-in-visual-studio-2015-update-1.aspx)  
  
## <a name="visual-studio-2015-rtm-debugger-ui-and-hotkey-changes"></a>Visual Studio 2015 RTM 调试程序 UI 和热键更改  
 异常和断点 UI 中有重大 UI 更改。  
  
### <a name="breakpoints"></a>断点  
 在 Visual Studio 2015 中，有配置断点的新方法，即 **“断点设置”** 窗口。  
  
 此处是主要“断点”窗口和热键的摘要：  
  
|功能|菜单位置|热键|  
|-------------|-------------------|------------|  
|新断点, 切换断点|**调试 / 切换断点**<br /><br /> 编辑器中的上下文菜单/“插入断点” <br /><br /> 单击左边缘|F9|  
|新函数断点|**调试 / 新断点 / 函数断点**|在 Visual Studio 2015 RTM （没有进行任何更新），使用 ALT + F9，B<br /><br /> 在 Visual Studio 2015 Update 1 及更高版本，使用 CTRL + B|  
|“断点” 窗口|**调试 / Windows / 断点**|Ctrl + Alt + B|  
|**“断点设置”**， **“条件”**|断点处的上下文菜单/ **“条件”**|Alt + F9 C|  
|**“断点设置”**， |断点处的上下文菜单/“操作” |无热键|  
  
 有关详细信息，请参阅以下文章：  
  
1.  [使用断点](../debugger/using-breakpoints.md)  
  
2.  [新断点配置体验](http://blogs.msdn.com/b/visualstudioalm/archive/2014/10/06/new-breakpoint-configuration-experience.aspx)  
  
3.  [断点配置体验](http://channel9.msdn.com/Events/Visual-Studio/Connect-event-2014/711)  
  
### <a name="exception-settings"></a>异常设置  
 新的 **“异常设置”** 窗口允许指定想要为单个异常或异常类别设置的异常处理类型。  
  
|功能|菜单位置|热键|  
|-------------|-------------------|------------|  
|**“异常设置”** 窗口|**调试 / Windows / 异常设置**|Ctrl + Alt + E|  
  
 有关详细信息，请参阅以下文章：  
  
1.  [管理调试器的异常](../debugger/managing-exceptions-with-the-debugger.md)  
  
2.  [新异常窗口](http://blogs.msdn.com/b/visualstudioalm/archive/2015/02/23/the-new-exception-settings-window-in-visual-studio-2015.aspx)  
  
### <a name="edit-and-continue"></a>编辑并继续  
 在 Visual Studio 2015 中，可以在“工具/选项/调试/常规”  页中设置“编辑并继续”。 在早期版本中，这些设置位于单独的选项类别中。  
  
### <a name="attach-to-process"></a>附加到进程  
 在 Visual Studio 2015 中，“附加到进程”命令只能从“调试”菜单获取。 在早期版本中，还可以从“工具”菜单获取该命令。 Ctrl + Alt + P 热键在所有版本中都起作用。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中进行调试](../debugger/debugging-in-visual-studio.md)



