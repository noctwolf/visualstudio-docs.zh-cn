---
title: 如何： 使用设计器禁用 ClickOnce 应用程序的 URL 激活 |Microsoft Docs
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
- disallowURLActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: a337a582-e67c-409a-b52e-607cd1a8fc57
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 6cc5571dffba9daa3ac1f5f78e354487cbc654fe
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477552"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer"></a>如何：使用设计器禁用 ClickOnce 应用程序的 URL 激活
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 禁用 URL 激活的 ClickOnce 应用程序使用设计器](https://docs.microsoft.com/visualstudio/deployment/how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer)。  
  
通常情况下，[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]从 Web 服务器安装后立即应用程序会自动启动。 出于安全原因，您可以决定禁用此行为，并告知用户启动应用程序从**启动**菜单相反。 以下过程描述了如何禁用 URL 激活。  
  
 此方法仅适用于从 Web 服务器安装到用户计算机上的 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 应用程序。 它不能用于仅联机应用程序，可以仅通过使用其 URL 启动。 只能联机使用的和已安装应用程序之间的差异的详细信息，请参阅[选择 ClickOnce 部署策略](../deployment/choosing-a-clickonce-deployment-strategy.md)。  
  
 此过程使用[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。 此外可通过完成此任务[!INCLUDE[winsdklong](../includes/winsdklong-md.md)]。 有关详细信息，请参阅[如何： 禁用 URL 激活的 ClickOnce 应用程序](../deployment/how-to-disable-url-activation-of-clickonce-applications.md)。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-disable-url-activation-for-your-application"></a>禁用应用程序的 URL 激活的步骤  
  
1.  右键单击项目名称**解决方案资源管理器**，然后单击**属性**。  
  
2.  上**属性**页上，单击**发布**选项卡。  
  
3.  单击“选项” 。  
  
4.  单击**清单**。  
  
5.  选择标记的复选框**阻止通过 URL 激活应用程序**。  
  
6.  部署应用程序。  
  
## <a name="see-also"></a>请参阅  
 [发布 ClickOnce 应用程序](../deployment/publishing-clickonce-applications.md)



