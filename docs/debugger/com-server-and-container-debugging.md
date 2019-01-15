---
title: 调试 COM 服务器和容器 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.com
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ActiveX control container debugging [Visual Studio]
- debugging ActiveX controls
- COM servers, debugging
- ActiveX controls, debugging
- COM [Visual Studio], debugging
ms.assetid: b7ce8696-ebb8-4354-a767-f76b8ada4ac1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4e67d5ed5fbab83edb9b2aeea99e22a71c52424e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53923976"
---
# <a name="com-server-and-container-debugging"></a>调试 COM 服务器和容器
COM 应用程序执行若干不直接受程序员控制的任务。 DLL 间的通信、对象的使用计数和剪贴板操作只是可能遇到意外行为的少数几个情况。 发生这种情况时，第一步是抓住问题的根源。  
  
 Visual Studio 调试器支持单步通过和单步执行容器和服务器。 这包括单步执行远程过程调用 (RPC) 的能力。  
  
##  <a name="BKMK_COMServerandContainerintheSameSolution"></a> 使用同一解决方案调试 COM 服务器和容器  
 可以使用同一解决方案中的两个项目来调试 COM 服务器和容器。 在每个项目和调试中设置适当的断点。 当容器对服务器进行调用而遇到断点时，容器将一直等到服务器代码返回（即等到完成调试）。  
  
 调试 COM 容器类似于调试标准程序。 一个不同的情况是当调试生成回调的事件时（如在容器应用程序上拖动数据）。 这种情况下，必须在回调函数中设置断点。  
  
##  <a name="BKMK_ServerApplicationWithoutContainerInformation"></a> 在没有容器信息的情况下调试服务器应用程序  
 如果不必或不想容器应用程序使用调试信息，那么开始调试服务器应用程序可分三步进行：  
  
1.  像对待普通的应用程序一样开始调试服务器。  
  
2.  按需要设置断点。  
  
3.  启动容器应用程序。  
  
##  <a name="BKMK_DebuggingaServerandDomainIsolationSDIApplication"></a> 调试服务器和域隔离 (SDI) 应用程序  
 如果调试的是 SDI 服务器应用程序，对于 C/C++、C# 或 Visual Basic 项目，必须在“项目属性页”对话框中的“命令行参数”属性中指定 `/Embedding` 或 `/Automation`。  
  
 使用这些命令行自变量，调试器可以像从容器中启动服务器应用程序一样启动它。 从程序管理器或文件管理器启动容器将导致容器使用在调试器中启动的服务器实例。  
  
 若要访问“项目属性页”对话框，请在解决方案资源管理器中右键单击项目，然后从快捷菜单中选择“属性”。 若要找到“命令行自变量”属性，请展开“配置属性”类别并单击“调试”页。  
  
## <a name="see-also"></a>请参阅  
 [调试 COM 和 ActiveX](../debugger/com-and-activex-debugging.md)