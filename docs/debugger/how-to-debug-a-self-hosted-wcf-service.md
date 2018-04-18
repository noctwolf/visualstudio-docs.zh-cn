---
title: 如何： 调试自我托管的 WCF 服务 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, self-hosted service
- WCF, debugging
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fb1fcd61c65b29a0ccb262b31a10847ebb80539d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>如何：调试自我托管的 WCF 服务
A*自我托管服务*是不会在 IIS、 WCF 服务主机内运行的 WCF 服务或[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]开发服务器。 若要调试自承载的 WCF 的最简单方法是配置[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以启动客户端和服务器，当你选择**启动调试**上**调试**菜单。  
  
 如果 WCF 服务自承载内部或不能以这种方式，如 NT 服务启动的进程无法使用此方法。 相反，你可以执行以下任一操作：  
  
-   手动将调试器附加到宿主进程。 有关详细信息，请参阅[附加到运行进程](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)。  
  
     — 或 —  
  
-   开始调试客户端，并随后单步执行对服务的调用。 这要求你启用调试的 app.config 文件中。 有关详细信息， [WCF 调试的限制](../debugger/limitations-on-wcf-debugging.md)。  
  
### <a name="to-start-both-client-and-host-from-visual-studio"></a>若要从 Visual Studio 中启动客户端和主机  
  
1.  创建[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]包含客户端和服务器项目的解决方案。  
  
2.  配置解决方案以在你选择时启动客户端和服务器进程**启动**上**调试**菜单。  
  
    1.  在**解决方案资源管理器**，右键单击解决方案名称。  
  
    2.  单击**设置启动项目**。  
  
    3.  在**解决方案\<名称 > 属性**对话框中，选择**多启动项目**。  
  
    4.  在**多启动项目**网格，请在服务器项目中，对应的行单击**操作**选择**启动**。  
  
    5.  在客户端项目对应的行，单击**操作**选择**启动**。  
  
    6.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [调试 WCF 服务](../debugger/debugging-wcf-services.md)   
 [WCF 调试的限制](../debugger/limitations-on-wcf-debugging.md)   
 [如何：单步执行 WCF 服务](../debugger/how-to-step-into-wcf-services.md)