---
title: TF 版本控制
description: 使用 Team Foundation 版本控制连接到 Team Foundation Server 或 Visual Studio Team Services。
author: asb3993
ms.author: amburns
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: f892209faeb06ca703d28016457e9ba4ab86ccda
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
---
# <a name="connecting-to-team-foundation-version-control"></a>连接到 Team Foundation 版本控制 

Visual Studio Team Services (VSTS) 和 Team Foundation Server (TFS) 提供两个版本控制模型：Git（分布式版本控制）和 Team Foundation 版本控制 (TFVC)（集中式版本控制）。 本文提供概述和借助 Visual Studio for Mac 使用 Team Foundation 版本控制的起点。

> [!NOTE]
> 请注意：Team Foundation 版本控制支持目前处于预览状态，某些功能尚未完全正常工作。 未来会有更多变化！

## <a name="requirements"></a>惠?

* Visual Studio for Mac 版本 7.5 或更高版本。
* Visual Studio Team Services 或 Team Foundation Server 2013 及更高版本
* Visual Studio Team Services 或 Team Foundation Server 中的项目，配置为使用 Team Foundation 版本控制。

## <a name="installation"></a>安装

从 Visual Studio for Mac 中，选择“Visual Studio”>“扩展...”菜单。 搜索“TF 版本控制”并安装 Team Foundation 版本控制扩展。 系统提示时，请重启 IDE。

## <a name="using-the-add-in"></a>使用加载项

安装扩展后，选择“版本控制”>“TFS/VSTS”>“连接到 Team Foundation 版本控制”菜单。 

![添加 TFVC 服务器](media/tfvc-add-remove-server.png)


选择 Visual Studio Team Services 或 Team Foundation Server 以开始使用：

![与 TFVC 服务器连接](media/tfvc-choose-server-type.png)

输入凭据： 

![登录到 TFVC 服务器](media/tfvc-login.png)

然后，选择要访问的项目： 

![选择项目](media/tfvc-choose-projects.png)

若要继续，请关闭对话框并使用“版本控制”>“TFS/VSTS”>“源代码管理器”菜单以浏览源。

> [!WARNING]
> 已知问题：在此预览版本中，第一次打开源代码管理器时，必须创建新的工作区。

![源资源管理器](media/tfvc-source-explorer.png)

从源代码管理器中，可以浏览服务器上的源代码，并执行以下操作：

- 管理工作区（创建、编辑或删除）。
- 在项目结构间导航。
- 映射项目。
- 获取项目。
- 锁定和解锁文件。
- 重命名文件。
- 删除文件。
- 添加新文件。
- 签出。
- 签入。
- 查看历史记录更改。
- 比较更改。

## <a name="creating-a-new-workspace"></a>创建一个新工作区

在源代码管理器中，单击“管理工作区”按钮。 

![管理工作区](media/tfvc-manage-workspaces.png)

单击“添加”创建新工作区。

![创建工作区](media/tfvc-create-workspace.png)

为工作区提供一个名称，然后单击“添加工作文件夹”，将项目映射到计算机上的本地文件夹。

完成后，单击“确定”，然后关闭“管理工作区”对话框。 现在可以通过源代码资源管理器获取文件并开始使用。