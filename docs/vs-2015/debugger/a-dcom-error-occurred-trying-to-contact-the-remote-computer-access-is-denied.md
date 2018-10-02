---
title: 尝试联系远程计算机时出现 DCOM 错误。 拒绝访问。 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.remote.dcom_access_denied
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, DCOM error
- remote DCOM access denied error
- DCOM, access errors
ms.assetid: 9d7dfc1b-9fe0-4f54-9c50-9c0e0f8358c5
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cabac4997480b626714c129daef0511643ae2a50
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482030"
---
# <a name="a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied"></a>尝试联系远程计算机时出现 DCOM 错误。 拒绝访问。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[尝试联系远程计算机时出现 DCOM 错误。访问被拒绝。](https://docs.microsoft.com/visualstudio/debugger/a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied).  
  
远程调试使用 DCOM 在以下情况下进行本地和远程计算机之间的通信：  
  
-   调试器设置为了“本机兼容性模式”  ，或在“工具/选项/调试”  页内选中了“托管兼容模式”    
  
-   调试的是托管 C++ (C++/CLI) 代码。  
  
-   在 Visual Studio 2013 中，在“工具”/“选项”/“调试”  页内选中了“启用本机编辑并继续”   
  
-   某些第三方调试方案  
  
 当 Visual Studio 进程无法通过 DCOM 针对远程调试器进程验证自己的身份（或提供的凭据被视为不足）时，将出现此错误。 以下一个或多个解决方法可解决此问题：  
  
-   关闭“本机兼容模式”   和“托管兼容模式” 。  
  
-   在 Visual Studio 2013 中，关闭“启用本机编辑并继续” 。  
  
-   重新启动这两台计算机。  
  
-   如果远程调试要求输入凭据，则选中该选项以保存凭据。  
  
## <a name="see-also"></a>请参阅  
 [远程调试错误和故障排除](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [远程调试](../debugger/remote-debugging.md)



