---
title: 创建 Visual Studio 的脱机安装 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- offline installation
- offline install
- ISO
ms.assetid: 85d65709-42be-449f-9663-914bf1045089
caps.latest.revision: 22
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 0f73247c02034d32a5843c69477f3fdcbdea4410
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49949625"
---
# <a name="create-an-offline-installation-of-visual-studio"></a>创建 Visual Studio 脱机安装缓存
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 2017 的最新文档，请参阅[在低带宽或不可靠的网络环境中安装 Visual Studio 2017](https://docs.microsoft.com/visualstudio/install/install-vs-inconsistent-quality-network)，或[创建网络安装的 Visual Studio 2017](https://docs.microsoft.com/visualstudio/install/create-a-network-installation-of-visual-studio)和[在脱机环境中安装 Visual Studio 2017 的特殊注意事项](https://docs.microsoft.com/visualstudio/install/install-visual-studio-in-offline-environment)。

此页介绍了如何安装 Visual Studio 2015 时未连接到 Internet。 但是，若要执行的"断开连接"的安装，您必须首先创建的脱机安装布局使用连接到 Internet 的计算机。 以下是使用方法。  

> [!IMPORTANT]
>  如果在脱机计算机正在运行 Windows 7 SP1 或 Windows Server 2008 R2，请参阅中的特殊说明[故障排除的脱机安装](#BKMK_tshoot)本主题的部分。  必须遵循这些说明*之前*安装 Visual Studio 2015。  

##  <a name="BKMK_Offline"></a> 通过创建脱机安装来安装  

#### <a name="to-create-an-offline-installation-layout"></a>若要创建脱机安装布局  

1.  选择你想要从安装的 Visual Studio 的版本[My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20Enterprise%202015)下载页。  

2.  你下载到的位置在文件系统上安装程序后，运行"\<可执行文件名称 > /layout"。  

     例如，运行： `vs_enterprise.exe /layout D:\VisualStudio2015`  

     通过使用`/layout`开关，你可以下载几乎所有的安装包，而不仅仅是适用于下载计算机。 此方法，您需要在任意位置运行此安装程序的文件，如果你想要安装原来没有安装的组件可能很有用。  

3.  在运行此命令后，将出现一个对话框，您可以更改想要驻留的脱机安装布局的文件夹。   接下来，单击**下载**按钮。  

     包下载成功后，您应看到一条消息，指出**安装成功 ！已成功获取所有指定组件。”**  

4.  找到你在前面指定的文件夹。 （例如，找到 D:\VisualStudio2015。）此文件夹包含将复制到共享位置或安装媒体所需的一切。  

    > [!CAUTION]
    >  目前，Android SDK 不支持脱机安装体验。 如果在未连接到 Internet 的计算机上安装 Android SDK 安装程序项，则安装可能失败。 有关详细信息，请参阅本主题中的"故障排除的脱机安装"部分。  

5.  从文件位置或安装媒体运行安装。  

## <a name="updating-an-offline-installation"></a>更新脱机安装  
 Microsoft Visual Studio 2015 发布了几个更新。 若要更新你的 Visual Studio 安装，只需下载想要从的版本从[My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20Enterprise%202015)下载页。 接下来，请按照本主题，若要创建新的脱机安装布局中所述的步骤，然后使用它来更新 Visual Studio 2015 的副本。  

##  <a name="BKMK_tshoot"></a> 故障排除的脱机安装  
 从脱机安装缓存进行脱机安装时，可能会看到提示无法安装某些组件和包的警告消息。 下表包含针对这些情况可能的解决方案。  


|                                                                                       组件或包                                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                   解决方案                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dotfuscator 和 Analytics 社区版 5.19.1 (Community、 Professional 和 Enterprise 版本的 Visual Studio 中，为上已安装**Windows 7 SP1**并**Windows Server 2008 R2**) |                                                                                                                                       如果在脱机计算机正在运行**Windows 7 SP1**或**Windows Server 2008 R2**，在安装 Visual Studio 2015 之前，必须执行以下步骤：<br /><br /> 1.配置文件或 web 服务器来下载 CTL 文件。<br /><br /> 2.  重定向 Microsoft 自动更新 URL 连接断开的环境。<br /><br /> 有关详细信息，请参阅[配置受信任的根和不允许的证书](https://technet.microsoft.com/library/dn265983.aspx)Microsoft TechNet 站点上的页。                                                                                                                                       |
|                                                                                  Android SDK 安装程序（API 级别）                                                                                   |                                                                        必须连接 Internet 才能安装 Android SDK（API 级别）包。 如果处于受限网络上，则在安装 Visual Studio 时必须允许访问以下 URL：<br /><br /> -   http://dl.google.com:443<br />-   http://dl-ssl.google.com:443<br />-   https://dl-ssl.google.com/android/repository/*<br /> <br />有关如何使用代理设置解决可能出现的问题的详细信息，请参阅[Visual Studio 2015 安装代理的故障 （Android SDK 安装程序）](https://blogs.msdn.microsoft.com/peterhauge/2016/09/22/visual-studio-2015-install-failures-android-sdk-setup-behind-a-proxy/)博客文章。                                                                         |
|                             Visual Studio Extensibility 项模板<br /><br /> 适用于 Visual Studio 的 GitHub 扩展<br /><br /> Visual Studio 的 PowerShell 工具                             | 如果你没有 internet 连接在安装 Visual Studio 2015 时，可以使用特殊的离线源生成脱机安装布局。 **注意：** 此特殊的数据源包含到 Visual Studio 2015 的最新更新。 <br /><br /> 若要创建特殊的离线源，请运行以下命令： /layout *Drive:* \VisualStudio2015 /overridefeeduri*源 xml URL*<br /><br /> 例如，对于英语语言的 Visual Studio 2015 Enterprise 中，特殊脱机源运行：<br /><br /> `vs_enterprise_ENU.exe /layout D:\VisualStudio2015 /overridefeeduri "http://go.microsoft.com/fwlink/?LinkID=785882&clcid0x409"`<br /><br /> 有关可用于在所选的语言中创建一个特殊离线源 Url 的完整列表，请参阅下表。 |

 使用以下 Url 创建特定于语言的特殊脱机源，上述表中所述。  


|       语言        |                            URL                            |
|-----------------------|-----------------------------------------------------------|
| 中文（简体）  | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x804 |
| 和 SharePoint 2010 显示的“中文(繁体)” | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x404 |
|         捷克语         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x405 |
|        德语         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x407 |
|        英语        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x409 |
|        西班牙语        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0xC0A |
|        法语         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x40C |
|        意大利语        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x410 |
|       日语        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x411 |
|        朝鲜语         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x412 |
|        波兰语         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x415 |
|      葡萄牙语       | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x416 |
|        俄语        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x419 |
|        土耳其语        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x41F |

## <a name="see-also"></a>请参阅  
 [安装 Visual Studio]()