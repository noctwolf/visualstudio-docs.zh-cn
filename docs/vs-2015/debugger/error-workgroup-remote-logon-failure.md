---
title: 错误： 工作组远程登录失败 |Microsoft Docs
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
- vs.debug.error.workgroup_remote_logon_failure
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- logon failure, remote debugging
- remote debugging, logon failure
ms.assetid: 7be2c5bb-40fe-48d6-8cfc-c231fbd3d64e
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 46d7043eba9d357f410d1a05655870ef5e1121d6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477544"
---
# <a name="error-workgroup-remote-logon-failure"></a>错误：工作组远程登录失败
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[错误： 工作组远程登录失败](https://docs.microsoft.com/visualstudio/debugger/error-workgroup-remote-logon-failure)。  
  
此错误显示如下：  
  
 登录失败: 未知的用户名或密码不正确  
  
 **原因**  
  
 当从工作组上的计算机进行调试并尝试连接到远程计算机时可能发生此错误。 可能的原因包括：  
  
-   远程计算机上没有匹配用户名和密码的帐户。  
  
-   如果在 Visual Studio 计算机和远程计算机在工作组上，此错误可能由默认值**本地安全策略**设置远程计算机上。 默认设置为**本地安全策略**设置为**仅来宾-本地用户以来宾身份验证**。 若要在此安装程序上进行调试，必须更改到在远程计算机上的设置**经典-本地用户以自己的身份验证**。  
  
> [!NOTE]
>  你必须是管理员才能执行以下任务。  
  
### <a name="to-open-the-local-security-policy-window"></a>打开“本地安全策略”窗口  
  
1.  启动**secpol.msc** Microsoft 管理控制台管理单元中。 在 Windows 搜索、Windows“运行”框中或命令提示符处键入 secpol.msc。  
  
### <a name="to-add-user-rights-assignments"></a>添加用户权限分配  
  
1.  打开 Loca  
  
2.  打开**本地安全策略**窗口。  
  
3.  展开**本地策略**文件夹。  
  
4.  单击**用户权限分配**。  
  
5.  在中**策略**列中，双击**调试程序**若要查看当前的本地组策略分配中**本地安全策略设置**对话框。  
  
     ![本地安全策略的用户权限](../debugger/media/dbg-err-localsecuritypolicy-userrightsdebugprograms.png "DBG_ERR_LocalSecurityPolicy_UserRightsDebugPrograms")  
  
6.  若要添加新用户，请单击**添加用户或组**按钮。  
  
### <a name="to-change-the-sharing-and-security-model"></a>更改“共享和安全模型”  
  
1.  打开**本地安全策略**窗口。  
  
2.  展开**本地策略**文件夹。  
  
3.  单击**安全选项**。  
  
4.  在中**策略**列中，双击**网络访问： 本地帐户的共享和安全模型**。  
  
5.  在中**网络访问： 本地帐户的共享和安全模型**对话框框中，将值更改为**经典-本地用户以自己的身份验证**单击**应用**按钮。  
  
     ![本地安全策略安全选项](../debugger/media/dbg-err-localsecuritypolicy-securityoptions-networkaccess.png "DBG_ERR_LocalSecurityPolicy_SecurityOptions_NetworkAccess")  
  
## <a name="see-also"></a>请参阅  
 [远程调试错误和故障排除](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [远程调试](../debugger/remote-debugging.md)



