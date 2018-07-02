---
title: TF 版本控制
description: 使用 Team Foundation 版本控制连接到 Team Foundation Server 或 Visual Studio Team Services。
author: asb3993
ms.author: amburns
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 58d0fc5c31b02574661f8b86a4ae8bcaf393be3a
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693768"
---
# <a name="connecting-to-team-foundation-version-control"></a>连接到 Team Foundation 版本控制 

> [!NOTE]
> 请注意：Team Foundation 版本控制支持目前处于预览状态，某些功能尚未完全正常工作。 我们衷心期待能在[开发者社区](https://developercommunity.visualstudio.com/spaces/41/index.html)收到你有关任何问题的反馈意见。 更多更改陆续到来！

Visual Studio Team Services (VSTS) 和 Team Foundation Server (TFS) 提供两个版本控制模型：Git（分布式版本控制）和 Team Foundation 版本控制 (TFVC)（集中式版本控制）。 本文提供概述和借助 Visual Studio for Mac 使用 Team Foundation 版本控制的起点。

## <a name="requirements"></a>要求

* Visual Studio for Mac 版本 7.5 或更高版本。
* Visual Studio Team Services 或 Team Foundation Server 2013 及更高版本
* Visual Studio Team Services 或 Team Foundation Server 中的项目，配置为使用 Team Foundation 版本控制。

## <a name="installation"></a>安装

在 Visual Studio for Mac 中，从菜单中选择“Visual Studio”>“扩展...”。 在“库”选项卡中，选择“版本控制”>“适用于 TFS 和 VSTS 的 Team Foundation 版本控制”，然后单击“安装...”：

  ![扩展管理器](media/tfvc-install.png) 

按照提示安装扩展。 安装后，重启 IDE。

## <a name="using-the-add-in"></a>使用加载项

安装扩展后，选择“版本控制”>“TFS/VSTS”>“连接到 Team Foundation 版本控制...”菜单项。 单击“添加”以添加新帐户： 

![添加 TFVC 服务器](media/tfvc-add-remove-server.png)

选择 Visual Studio Team Services 或 Team Foundation Server 以开始使用：

![与 TFVC 服务器连接](media/tfvc-choose-server-type.png)

输入凭据，然后单击“登录”： 

![登录到 TFVC 服务器](media/tfvc-login.png)

成功登录后，选择要访问的项目并按“确定”： 

![选择项目](media/tfvc-choose-projects.png)

选择“版本控制”>“TFS/VSTS”>“源代码管理器”菜单项，打开允许浏览源的源代码管理器。

> [!IMPORTANT]
> **已知问题**：在此预览版本中，首次打开源代码管理器时，必须[创建新工作区](#creating-a-new-workspace)。

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

单击“添加”按钮以创建新的工作区。

![创建工作区](media/tfvc-create-workspace.png)

为工作区提供一个名称，然后单击“添加工作文件夹”，将项目映射到计算机上的本地文件夹。

完成后，单击“确定”，然后关闭“管理工作区”对话框。 现在可以通过源代码资源管理器获取文件并开始使用。

## <a name="troubleshooting"></a>疑难解答

### <a name="problems-using-basic-authentication"></a>使用基本身份验证的问题

下面提供一些可通过服务器执行身份验证的其他几个选项：

- Oauth
- Basic
- Ntlm

为了能够使用基本身份验证，需要在 VSTS 中启用“其他身份验证凭据”，具体步骤如下：

1. 以帐户所有者身份登录到 VSTS 帐户 (https://{youraccount}.visualstudio.com)。
2. 在帐户工具栏中，选择齿轮图标，然后选择“策略”：![选中的策略设置](media/tfvc-auth2.png) 
3. 查看应用程序连接设置。 根据安全策略（![选中的策略设置选项](media/tfvc-auth.png)）更改这些设置  

### <a name="i-do-not-see-anything-in-tfvc"></a>我在 TFVC 中没有看到任何内容

要在开发计算机上设置 Team Foundation 版本控制 (TFVC)，必须按照[创建新工作区](#creating-a-new-workspace)部分所述创建工作区。

在源代码管理器中，按“管理工作区”按钮。 按照步骤将团队项目映射到开发计算机上的文件夹。

### <a name="i-do-not-see-any--all-of-my-projects"></a>我没有看到任何/所有项目

身份验证后，应该可以看到项目列表。 默认情况下，只显示 TFS 项目。 要查看其他类型的项目，请选中“查看所有项目”框。

请记住，只有权限正确，才会显示服务器上的项目。

#### <a name="i-am-getting-the-error-cannot-create-the-workspace-please-try-again"></a>我收到“无法创建工作区， 请重试”错误

尝试[创建新工作区](#creating-a-new-workspace)时，应确保满足以下条件：

- 工作区名称中不可使用无效字符。
- 名称必须少于 64 个字符。
- 任何其他工作区都不能使用本地路径。