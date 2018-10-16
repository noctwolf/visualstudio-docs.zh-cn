---
title: 如何： 指定 ClickOnce 脱机或联机安装模式 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: b243811f2c6c36266443cd34e0e37ddd01390f87
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49266055"
---
# <a name="how-to-specify-the-clickonce-offline-or-online-install-mode"></a>如何：指定 ClickOnce 脱机或联机安装模式
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`Install Mode`为[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]应用程序确定应用程序是脱机还是联机。 当你选择**应用程序仅可在线**，用户必须有权访问[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]发布位置 （Web 页面或文件共享） 才能运行该应用程序。 当你选择**应用程序也可以脱机使用**，应用程序将条目添加到**启动**菜单并**添加或删除程序**对话框; 用户是能够在不连接时运行该应用程序。  
  
 `Install Mode`可以设置**发布**页**项目设计器**。  
  
 **请注意**`Install Mode`也可以使用发布向导设置。 有关详细信息，请参阅[如何： 发布 ClickOnce 应用程序使用发布向导](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)。  
  
### <a name="to-make-a-clickonce-application-available-online-only"></a>若要使 ClickOnce 应用程序可联机仅  
  
1.  在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。  
  
2.  单击**发布**选项卡。  
  
3.  在中**安装模式和设置**区域中，单击**应用程序仅可在线**选项按钮。  
  
### <a name="to-make-a-clickonce-application-available-online-or-offline"></a>若要使 ClickOnce 应用程序可在联机或脱机  
  
1.  在“解决方案资源管理器” 中选择了项目的情况下，在“项目”  菜单上单击“属性” 。  
  
2.  单击**发布**选项卡。  
  
3.  在中**安装模式和设置**区域中，单击**应用程序也可以脱机使用**选项按钮。  
  
     安装后，应用程序添加到条目**启动**菜单并对其**添加或删除程序**控制面板中。  
  
## <a name="see-also"></a>请参阅  
 [发布 ClickOnce 应用程序](../deployment/publishing-clickonce-applications.md)   
 [如何：使用发布向导发布 ClickOnce 应用程序](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [选择 ClickOnce 部署策略](../deployment/choosing-a-clickonce-deployment-strategy.md)



