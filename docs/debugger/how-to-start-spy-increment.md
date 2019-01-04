---
title: 如何：启动 Spy + + |Microsoft Docs
ms.custom: ''
ms.date: 12/16/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Spy++, starting
ms.assetid: 1d36813a-dc2a-4fda-9b3d-a38928a62ced
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5143c34f0c344fecec82a5d08b2e7fb9b95ac1bc
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2018
ms.locfileid: "53646862"
---
# <a name="how-to-start-spy"></a>如何：启动 Spy++

您可以启动 Spy + + 通过 Visual Studio 或命令提示符处。  
  
 当你启动 Spy + +，如果显示一条消息询问权更改计算机，请选中**是**。  
  
> [!NOTE]
>  可以运行 Spy + + 的一个实例。 如果尝试启动第二个实例，它只会导致当前正在运行的实例，若要获取焦点。

## <a name="prerequisites"></a>系统必备

Spy + + 需要以下组件。 可以从 Visual Studio 安装程序选择这些组件，通过选择**各个组件**选项卡，然后选择以下组件。

* 在调试和测试，选择**c + + 分析工具**
* 在开发活动下选择**Visual Studio c + + 核心功能**

如果所做的任何更改，请按照提示安装这些组件。
  
## <a name="start-spy-from-visual-studio"></a>从 Visual Studio 启动 Spy + +
  
上**工具**菜单中，选择**Spy + +**。  
  
因为 Spy + + 独立地运行在启动后，你可以关闭 Visual Studio。  
  
> [!NOTE]
>  当使用 Spy + + 中记录消息时，它可能会导致操作系统执行得更慢。  
  
## <a name="start-spy-at-a-command-prompt"></a>命令提示符处启动 Spy + +  
  
1.  在命令提示符窗口中，将目录更改到包含 spyxx.exe 的文件夹。 通常情况下，此文件夹的路径是...\\ *Visual Studio 安装文件夹*\Common7\Tools\\。  
  
2.  输入**spyxx.exe**。 
  
## <a name="see-also"></a>请参阅  
 [使用 Spy++](../debugger/using-spy-increment.md)   
 [Spy++ 视图](../debugger/spy-increment-views.md)   
 [Spy++ 参考](../debugger/spy-increment-reference.md)