---
title: 使用 Web 部署的部署
description: 部署应用程序使用 Visual Studio 中的 Web 部署
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 4ef232e64f308699c73c60cbe5b155f1d4ebb725
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34794185"
---
如果你安装 Web 部署使用 Web 平台安装程序，你可以部署该应用程序直接从 Visual Studio。

1. 使用管理员权限启动 Visual Studio 并重新打开该项目。

    部署使用 Web 部署对应用程序需要管理员权限。

1. 在“解决方案资源管理器” 中，右键单击项目节点并选择“发布” 。

    如果你之前配置任何发布的配置文件，**发布**窗格中显示。 单击**新的配置文件**。

1. 有关**选择发布目标**，选择**IIS，FTP，等**单击**发布**。

    ![RemoteDBG_Publish_IISl](../../debugger/media/remotedbg_iis_profile.png "RemoteDBG_Publish_IIS")

1. IIS 设置中输入更正配置参数。

    ![RemoteDBG_Publish_WebDeployl](../../debugger/media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    如果主机名不能解决当你尝试验证下一步中的步骤**服务器**文本框中，请尝试 IP 地址。 包括`http://`作为前缀的**服务器**字段。  请确保使用在端口 80**服务器**文本框中，并确保端口 80 和端口 8172 在防火墙中打开。

1. 选择**验证**。 如果连接安装验证，你可以尝试发布。

1. 单击**发布**发布该应用程序。

    输出选项卡将显示是否发布已成功，以及你的浏览器然后打开应用程序。

    如果你收到一提的是 Web 部署错误，重新检查 Web 部署安装步骤，请确保正确的端口已打开 （Web 部署还需要端口 8172 要在服务器上打开）。

    如果应用程序已成功部署，但不能正常运行，可能有 IIS 配置，您的 ASP.NET 安装，或者你的 Web 站点配置的问题。 在 Windows Server 中，打开从 IIS 的网站的更具体的错误消息，然后重新检查之前的步骤。
