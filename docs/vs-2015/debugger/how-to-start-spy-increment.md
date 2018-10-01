---
title: 如何： 启动 Spy + + |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Spy++, starting
ms.assetid: 1d36813a-dc2a-4fda-9b3d-a38928a62ced
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9eb5d8cd8a5ca0ba32f59e483265942379eb3122
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476787"
---
# <a name="how-to-start-spy"></a>如何：启动 Spy++
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 启动 Spy + +](https://docs.microsoft.com/visualstudio/debugger/how-to-start-spy-increment)。  
  
您可以启动 Spy + + 通过 Visual Studio 或命令提示符处。  
  
 当你启动 Spy + +，如果显示一条消息询问权限对计算机进行更改，请单击**是**。  
  
> [!NOTE]
>  可以运行 Spy + + 的一个实例。 如果你尝试运行另一个实例，它只会导致当前正在运行的实例，若要获取焦点。  
  
### <a name="to-start-spy-from-visual-studio"></a>若要从 Visual Studio 启动 Spy + +  
  
-   上**工具**菜单上，单击**Spy + +**。  
  
     因为 Spy + + 独立运行，在启动后，你可以关闭 Visual Studio。  
  
    > [!NOTE]
    >  当使用 Spy + + 中记录消息时，它可能会导致操作系统执行得更慢。  
  
### <a name="to-start-spy-at-a-command-prompt"></a>若要在命令提示符处启动 Spy + +  
  
1.  在命令提示符窗口中，将目录更改到包含 spyxx.exe 的文件夹。 通常情况下，此文件夹的路径是...\\ *Visual Studio 安装文件夹*\Common7\Tools\\。  
  
2.  类型**spyxx.exe** ，然后按 ENTER。  
  
## <a name="see-also"></a>请参阅  
 [使用 Spy + +](../debugger/using-spy-increment.md)   
 [Spy + + 视图](../debugger/spy-increment-views.md)   
 [Spy++ 参考](../debugger/spy-increment-reference.md)



