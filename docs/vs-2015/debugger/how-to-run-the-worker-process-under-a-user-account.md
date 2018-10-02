---
title: 如何： 运行辅助进程的用户帐户下 |Microsoft Docs
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
helpviewer_keywords:
- user accounts, aspnet_wp.exe
- ASP.NET, debugging Web applications
- tools, aspnet_wp.exe
- ASP.NET, tools
- aspnet_wp.exe
ms.assetid: b58e97b1-e62a-4318-aea4-52276ea20735
caps.latest.revision: 35
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 08ac00384110cc73175286365fef6ee4b67a0170
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471210"
---
# <a name="how-to-run-the-worker-process-under-a-user-account"></a>如何：在用户帐户下运行辅助进程
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 运行辅助进程以用户帐户](https://docs.microsoft.com/visualstudio/debugger/how-to-run-the-worker-process-under-a-user-account)。  
  
若要设置计算机以便在某个用户帐户下运行 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 辅助进程（aspnet_wp.exe 或 w3wp.exe），请执行下列步骤。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-run-aspnetwpexe-under-a-user-account"></a>以用户帐户运行 aspnet_wp.exe  
  
1.  打开 machine.config 文件，此文件位于计算机上运行时安装路径下的 CONFIG 文件夹中。  
  
2.  查找&lt;processModel&gt;部分，并将用户和密码属性更改为的名称和要用于运行 aspnet_wp.exe 的用户帐户的密码。  
  
3.  保存 machine.config 文件。  
  
4.  在 [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)] 上，默认情况下已安装 IIS 6.0。 相应的辅助进程是 w3wp.exe。若要在 IIS 6.0 模式下运行并将 aspnet_wp.exe 用作辅助进程，必须执行下列步骤：  
  
    1.  单击 **“开始”**，单击 **“管理工具”** ，然后选择 **“Internet 信息服务”**。  
  
    2.  在 **“Internet 信息服务”** 对话框中，右击 **“网站”** 文件夹并选择 **“属性”**。  
  
    3.  在 **“网站属性”** 对话框中选择 **“服务”**。  
  
    4.  选择 **“以 IIS6.0 隔离模式运行 WWW 服务”**。  
  
    5.  关闭 **“属性”** 对话框和 **“Internet 服务管理器”**。  
  
5.  打开 Windows 命令提示窗口，通过运行下面的命令重置服务器：  
  
    ```  
    iisreset  
    ```  
    — 或 —  
  
    ```  
    net stop iisadmin /y  
    net start w3svc  
    ```  
  
6.  找到 Temporary [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Files 文件夹，它应位于 CONFIG 文件夹所在的路径中。 右键单击 Temporary [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Files 文件夹，然后选择**属性**快捷菜单上。  
  
7.  在 **“临时 ASP.NET 文件属性”** 对话框中单击 **“安全性”** 选项卡。  
  
8.  单击 **“高级”**。  
  
9. 在 **“临时 ASP.Net 文件的高级安全设置”** 对话框中单击 **“添加”**。  
  
    将出现 **“选择用户、计算机或组”** 对话框。  
  
10. 在 **“输入要选择的对象名称”** 框中键入用户名，然后单击 **“确定”**。 用户名必须遵循以下格式：域名\用户名。  
  
11. 在 **“临时 ASP.Net 文件的权限项”** 对话框中，授予用户 **“完全控制”**，然后单击 **“确定”** 以关闭 **“临时 ASP.Net 文件项”** 对话框。  
  
12. 将出现 **“安全性”** 对话框，询问是否确实要更改系统文件夹的权限。 单击 **“是”**。  
  
13. 单击 **“确定”** 以关闭 **“临时 ASP.NET 文件属性”** 对话框。  
  
## <a name="see-also"></a>请参阅  
[ASP.NET 调试：系统要求](../debugger/aspnet-debugging-system-requirements.md)  
  




