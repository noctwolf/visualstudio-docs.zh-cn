---
title: 如何： 安装特定版本的 Visual Studio |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- install a specific release, Visual Studio
ms.assetid: d69ad0f8-f0a0-438e-a0ef-777c4868f139
caps.latest.revision: 20
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 25939a2ab8c98830c00c19b3e7c76c686a2a28ea
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49289910"
---
# <a name="how-to-install-a-specific-release-of-visual-studio"></a>如何：安装特定版本的 Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

我们会经常更新 Visual Studio 安装程序，以便你可以获得可选功能的最新优化版本。  但是，如果你想要安装 Visual Studio 2015 的早期版本（例如，包括 iOS 支持但为 Update 1 之前版本的 Visual Studio），则必须强制 Visual Studio 安装程序使用其功能清单文件的早期版本。 本文介绍了执行该操作的方法。  
  
## <a name="installing-the-current-release"></a>安装当前版本  
 自 Visual Studio 2015 的初始版本，我们已更新的安装引擎和清单文件数次。  这意味着，如果下载 web 安装程序从[Visual Studio 下载](https://www.visualstudio.com/downloads/download-visual-studio-vs)干净的、 已连接 internet 的计算机上的网站，安装程序安装最新的 Visual Studio 2015 更新包括最新的产品改进以及更高版本，最新版本的可选功能和工具。  
  
## <a name="installing-earlier-releases"></a>安装早期版本  
 可以创建并装载 ISO 映像，也可以下载并启动直接从安装程序[My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20enterprise%202015)然后追加其他命令行参数的.exe 文件 (例如 /CustomInstallPath、 / 完整，/ InstallSelectableItems，只显示，等等。)若要控制 Visual Studio 的安装方式。  
  
 下表包括某些特定的时间点方案和必须传递给 Enterprise edition 安装程序所需的命令行参数。 （这些参数也适用于 Community 或 Professional 版安装程序。）  
  
|Visual Studio 2015 版本|运行内容|要使用的命令行|安装程序执行的操作|  
|--------------------------------|-----------------|--------------------------|---------------------|  
|Visual Studio Enterprise（最新公开发布的版本）|使用更新的 visual Studio Enterprise (可从[My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20enterprise%202015))|`vs_enterprise.exe` **注意：** 此安装的默认行为提供了最新的可选功能，因此，不需要任何命令行参数。|Visual Studio 安装程序将使用最新的 feed.xml 并安装最新的文件|  
|Visual Studio Enterprise Update 3 (不需任何进一步的更新 3 纪元更新原始 Update 3)|Visual Studio Enterprise RTM（可从 [MSDN 订阅下载页](https://msdn.microsoft.com/subscriptions/downloads/)获取）|`vs_enterprise.exe /OverrideFeedURI http://download.microsoft.com/download/6/B/B/6BBD3561-D764-4F39-AB8E-05356A122545/20160628.2/enu/feed.xml`|Visual Studio 安装程序将使用提供的 Update 3 发布时的 feed.xml|  
|Visual Studio Enterprise Update 2 （原始 Update 2，但更新了该之前更新 3）|Visual Studio Enterprise RTM（可从 [MSDN 订阅下载页](https://msdn.microsoft.com/subscriptions/downloads/)获取）|`vs_enterprise.exe /OverrideFeedURI http://download.microsoft.com/download/6/B/B/6BBD3561-D764-4F39-AB8E-05356A122545/20160620.2/enu/feed.xml`|Visual Studio 安装程序将使用提供当前发布的 Update 3 之前的 feed.xml|  
|Visual Studio Enterprise (不需任何进一步的更新 2 纪元更新原始 Update 2)|Visual Studio Enterprise RTM（可从 [MSDN 订阅下载页](https://msdn.microsoft.com/subscriptions/downloads/)获取）|`vs_enterprise.exe /OverrideFeedURI http://download.microsoft.com/download/0/6/B/06BB0C5C-C767-4250-91DA-AB463377597E/20160405.3/enu/feed.xml`|Visual Studio 安装程序将使用提供的 Update 2 发布时的 feed.xml|  
|Visual Studio Enterprise Update 1 （原始 Update 1，但更新了该之前更新 2）|Visual Studio Enterprise RTM（可从 [MSDN 订阅下载页](https://msdn.microsoft.com/subscriptions/downloads/)获取）|`vs_enterprise.exe /OverrideFeedURI http://download.microsoft.com/download/3/2/A/32A1974F-D236-43C1-8981-97DDCBAEF14A/20160225.3/enu/feed.xml`|Visual Studio 安装程序将使用提供当前发布的 Update 2 之前的 feed.xml|  
|Visual Studio Enterprise Update 1（原始 Update 1，不包含任何 Update 1 之后的更新）|Visual Studio Enterprise RTM（可从 [MSDN 订阅下载页](https://msdn.microsoft.com/subscriptions/downloads/)获取）|`vs_enterprise.exe /OverrideFeedURI https://download.microsoft.com/download/3/2/A/32A1974F-D236-43C1-8981-97DDCBAEF14A/20151201.1/enu/feed.xml`|Visual Studio 安装程序将使用提供的 Update 1 发布时的 feed.xml|  
|Visual Studio Enterprise（原始 RTM，但带有 Update 1 之前的更新）|Visual Studio Enterprise RTM（可从  [MSDN 订阅下载页](https://msdn.microsoft.com/en-us/subscriptions/downloads/)获取）|`vs_enterprise.exe /OverrideFeedURI https://download.microsoft.com/download/3/6/1/36188D5F-479F-4A46-BF55-6AE5928D1EBB/20151102.3/enu/feed.xml`|Visual Studio 安装程序将使用发布 Update 1 之前的最新 feed.xml|  
|Visual Studio Enterprise（原始 RTM，不包含任何更新）|Visual Studio Enterprise RTM（可从 [MSDN 订阅下载页](https://msdn.microsoft.com/subscriptions/downloads/)获取）|`vs_enterprise.exe /OverrideFeedURI https://download.microsoft.com/download/5/7/B/57BF5016-E4F0-4EB5-BE27-2BFA87E7723F/20150713.1/enu/feed.xml`|Visual Studio 安装程序将使用提供的 RTM 发布时的 feed.xml|  
  
> [!IMPORTANT]
>  根据你想要使用的语言，请将“enu”（英语）替换为以下值之一：  
>   
>  -   chs（简体中文）  
> -   cht（繁体中文）  
> -   csy（捷克语）  
> -   deu（德语）  
> -   esn（西班牙语）  
> -   fra（法语）  
> -   ita（意大利语）  
> -   jpa（日语）  
> -   kor（朝鲜语）  
> -   plk（波兰语）  
> -   ptb（葡萄牙语）  
> -   rus（俄语）  
> -   trk（土耳其语）  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 管理员指南](../install/visual-studio-administrator-guide.md)