---
title: 错误： 您没有检查进程的权限&#39;s 标识 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
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
ms.assetid: 6233d060-85b8-42be-ae5f-bde7e1d0f241
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b4aafd6215c868ff93108e3b170999a8d028e2df
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476821"
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>错误： 您没有检查进程的权限&#39;s 标识
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[错误： 没有检查进程的权限&#39;s 标识](https://docs.microsoft.com/visualstudio/debugger/error-you-do-not-have-permission-to-inspect-the-process-s-identity)。  
  
您没有检查进程标识的权限。 这可能是您系统的配置造成的。  
  
 调试器无法检查进程标识，而进程标识是调试的必备信息。 最有可能的原因是“终端服务”被禁用了。 默认情况下，“终端服务”服务是处于启用状态的。 您可按照以下步骤重新启用该服务。  
  
### <a name="to-enable-terminal-services"></a>启用“终端服务”  
  
1.  单击**启动**，然后选择**控制面板**。  
  
2.  在控制面板中，选择**切换到经典视图**，如有必要，然后双击**管理工具**。  
  
3.  在中**管理工具**窗口中，双击**计算机管理**。  
  
4.  在计算机管理窗口中，展开**服务和应用程序**节点。  
  
5.  下**服务和应用程序**，单击**服务**。  
  
     右侧窗格中将出现一个服务列表。  
  
6.  在中**Services**列表中，右键单击**终端服务**，然后选择**属性**。  
  
7.  在中**Terminal Services 的属性**窗口中，转到**常规**选项卡并设置**启动类型**到**手动**。  
  
8.  单击 **“确定”**。  
  
9. 重新启动计算机。  
  
     此过程不会自动启用远程桌面。 如果要启用您计算机上的远程桌面，还要执行下面的步骤。  
  
### <a name="to-enable-remote-desktop"></a>启用远程桌面  
  
1.  单击**启动**，然后右击**我的电脑**。  
  
2.  选择“属性”。  
  
     **系统属性**显示窗口。  
  
3.  单击**远程**。  
  
4.  下**远程桌面**，选择**允许用户远程连接到此计算机**。  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>请参阅  
 [远程调试错误和疑难解答](../debugger/remote-debugging-errors-and-troubleshooting.md)



