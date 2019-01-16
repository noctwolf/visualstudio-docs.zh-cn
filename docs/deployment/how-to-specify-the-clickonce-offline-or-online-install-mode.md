---
title: 如何：指定 ClickOnce 脱机或联机安装模式 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, specifying install mode
- install mode
- online applications
- offline applications
- ClickOnce install mode
ms.assetid: 0aee5fc1-e966-4bda-9b8f-d9997aeaa779
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bd0b985d7629ec282de4946ab89fef06e97c5921
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53889009"
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>如何：指定 ClickOnce 脱机或联机安装模式
`Install Mode`为[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序确定应用程序是脱机还是联机。 当你选择**应用程序仅可在线**，用户必须有权访问[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]发布位置 （Web 页面或文件共享） 才能运行该应用程序。 当你选择**应用程序也可以脱机使用**，应用程序将条目添加到**启动**菜单并**添加或删除程序**对话框; 用户是能够在不连接时运行该应用程序。  
  
 `Install Mode`可以设置**发布**页**项目设计器**。  
  
 **请注意**`Install Mode`也可以使用发布向导设置。 有关更多信息，请参见[如何：使用发布向导发布 ClickOnce 应用程序](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)。  
  
### <a name="to-make-a-clickonce-application-available-online-only"></a>若要使 ClickOnce 应用程序可联机仅  
  
1.  在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。  
  
2.  单击“发布”选项卡。  
  
3.  在中**安装模式和设置**区域中，单击**应用程序仅可在线**选项按钮。  
  
### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>若要使 ClickOnce 应用程序可在联机或脱机  
  
1.  在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。  
  
2.  单击“发布”选项卡。  
  
3.  在中**安装模式和设置**区域中，单击**应用程序也可以脱机使用**选项按钮。  
  
     安装后，应用程序添加到条目**启动**菜单并对其**添加或删除程序**控制面板中。  
  
## <a name="see-also"></a>请参阅  
 [发布 ClickOnce 应用程序](../deployment/publishing-clickonce-applications.md)   
 [如何：使用发布向导发布 ClickOnce 应用程序](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [选择 ClickOnce 部署策略](../deployment/choosing-a-clickonce-deployment-strategy.md)