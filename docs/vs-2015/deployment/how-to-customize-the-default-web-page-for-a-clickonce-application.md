---
title: 如何： 为 ClickOnce 应用程序自定义默认的网页 |Microsoft Docs
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
- Publish.htm Web page
- ClickOnce deployment default Web page
- deploying applications [ClickOnce], publishing
- publishing, ClickOnce
ms.assetid: 418de18c-bee9-4f24-9cd9-0252d175070d
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: b87019a824acada616865fd65cfd6aade8aa6ec9
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49243420"
---
# <a name="how-to-customize-the-default-web-page-for-a-clickonce-application"></a>如何：自定义 ClickOnce 应用程序的默认网页
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在发布 ClickOnce 应用程序到 Web，Web 页自动生成并随应用程序一起发布。 默认页包含的应用程序和用于安装应用程序、 安装必备组件，或访问 MSDN 上的帮助链接的名称。  
  
> [!NOTE]
>  在页看到的实际链接取决于计算机页查看位置以及要包括的先决条件。  
  
 Web 页面的默认名称是 Publish.htm;可以更改中的名称**项目设计器**。 有关详细信息，请参阅[如何： 指定 ClickOnce 应用程序的发布页](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)。  
  
 仅当检测到较新版本发布 Publish.htm 网页。  
  
> [!NOTE]
>  对所做的更改你**发布**设置将不会影响 Publish.htm 页中的，有一个例外： 如果添加或删除系统必备组件在最初发布后，系统必备组件的列表将不再准确。 你将需要编辑的先决条件的链接，以反映所做的更改的文本。  
  
### <a name="to-customize-the-publish-web-page"></a>若要自定义 Web 发布页  
  
1.  发布 ClickOnce 应用程序到 Web 位置。 有关详细信息，请参阅[如何： 发布 ClickOnce 应用程序使用发布向导](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)。  
  
2.  在 Web 服务器上，在 Visual Web 设计器或另一个 HTML 编辑器中打开 Publish.htm 文件。  
  
3.  自定义为所需的页，并将其保存。  
  
4.  可选。 若要阻止 Visual Studio 覆盖您自定义的发布的网页，取消选中**自动生成部署网页后每个发布**发布选项对话框中。  
  
## <a name="see-also"></a>请参阅  
 [ClickOnce 安全和部署](../deployment/clickonce-security-and-deployment.md)   
 [发布 ClickOnce 应用程序](../deployment/publishing-clickonce-applications.md)   
 [如何：与 ClickOnce 应用程序一起安装必备组件](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [如何：指定 ClickOnce 应用程序的发布页](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)



