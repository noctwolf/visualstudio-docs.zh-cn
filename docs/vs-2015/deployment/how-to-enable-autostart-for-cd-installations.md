---
title: 如何： 为 CD 安装启用自动启动 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
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
- ClickOnce deployment, AutoStart
- ClickOnce deployment, installation on CD or DVD
- deploying applications [ClickOnce], installation on CD or DVD
ms.assetid: caaec619-900c-4790-90e3-8c91f5347635
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 7a0f7228e4340763104f38dc56e5e8603ed85408
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470549"
---
# <a name="how-to-enable-autostart-for-cd-installations"></a>如何：为 CD 安装启用自动启动
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 为 CD 安装启用自动启动](https://docs.microsoft.com/visualstudio/deployment/how-to-enable-autostart-for-cd-installations)。  
  
在部署时[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]通过可移动媒体，如 CD-ROM 或 DVD-ROM 的应用程序，可以启用`AutoStart`以便[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]插入媒体时自动启动应用程序。  
  
 `AutoStart` 在上启用**发布**页**项目设计器**。  
  
### <a name="to-enable-autostart"></a>若要启用自动启动  
  
1.  在“解决方案资源管理器” 中选择一个项目，然后在“项目”  菜单上单击“属性” 。  
  
2.  单击**发布**选项卡。  
  
3.  单击**选项**按钮。  
  
     **发布选项**对话框随即出现。  
  
4.  单击**部署**。  
  
5.  选择**对于 CD 安装，插入 CD 时自动启动安装程序**复选框。  
  
     发布应用程序时，才能将 Autorun.inf 文件复制到发布位置。  
  
## <a name="see-also"></a>请参阅  
 [发布 ClickOnce 应用程序](../deployment/publishing-clickonce-applications.md)   
 [如何：使用发布向导发布 ClickOnce 应用程序](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



