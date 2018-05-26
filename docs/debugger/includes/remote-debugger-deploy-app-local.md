---
title: 将部署到本地文件夹
description: 将应用部署到本地文件夹
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: bd477fec033eb75f626401586abfd10c798601ef
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
1. 在**解决方案资源管理器**，右键单击项目节点并选择**发布**(对于 Web 窗体，**发布 Web 应用**)。

    如果你之前配置任何发布的配置文件，**发布**窗格中显示。 单击**新的配置文件**。

1. 在**发布**对话框中，选择**文件夹**，单击**浏览**，并创建一个新文件夹中， **C:\Publish**。

    ![RemoteDBG_Publish_Local](../media/remotedbg_publish_local.png "RemoteDBG_Publish_Local")

    对于 Web 窗体应用中，选择**自定义**在发布对话框中，输入配置文件名称，然后选择**确定**。

1. 单击**创建配置文件**下拉列表中 (**发布**是默认值)。

1. 在**发布**对话框中，单击**设置**链接，，然后选择**设置**选项卡。

1. 将配置设置为**调试**，选择**删除所有现有的文件发布前**，然后单击**保存**。

    > [!NOTE]
    > 如果你使用的发布版本，则禁用调试在 web.config 文件中，在发布时。

1. 单击“发布” 。

    ![RemoteDBG_Publish_Debug_Config](../media/remotedbg_publish_debug_config.png "RemoteDBG_Publish_Debug_Config")
    
    应用程序发布**调试**到本地文件夹的项目配置。 进度将显示在输出窗口中。

1. 从 Visual Studio 计算机的 ASP.NET 项目目录复制到对 ASP.NET 应用程序配置的本地目录 (在此示例中， **C:\Publish**) Windows Server 计算机上。 在本教程中，我们假设你要手动复制，但你可以使用 PowerShell、 Xcopy 或 Robocopy 等其他工具。

    > [!CAUTION]
    >  如果你需要更改代码或重新生成，你必须重新发布并重复此步骤。 复制到远程计算机的可执行文件必须与你的本地源和符号完全匹配。    如果你不执行此将收到`cannot find or open the PDB file`警告 Visual Studio 中，当你尝试调试进程。

1. 在 Windows 服务器上，验证可以正确运行该应用，通过在浏览器中打开应用程序。

    如果应用程序无法正常运行，安装在你的服务器和您的 Visual Studio 计算机上的 ASP.NET 版本之间可能有不匹配，或你可能遇到的问题与您的 IIS 或网站配置。 重新检查之前的步骤。
