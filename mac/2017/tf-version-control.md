---
title: Team Foundation 版本控制 (TFVC)
description: 使用 Team Foundation 版本控制 (TFVC) 连接到 Team Foundation Server 或 Azure DevOps Services。
author: conceptdev
ms.author: crdun
ms.date: 09/05/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 73c068ed1fcd03564638961e3d4e6dce7f7d6ed2
ms.sourcegitcommit: aeb1a1135dd789551e15aa5124099a5fe3f0f32b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66501227"
---
# <a name="connecting-to-team-foundation-version-control"></a>连接到 Team Foundation 版本控制

> [!NOTE]
> Team Foundation 版本控制支持目前处于预览状态，某些功能尚未完全正常工作。 我们衷心期待能在[开发者社区](https://developercommunity.visualstudio.com/spaces/41/index.html)收到你有关任何问题的反馈意见。 更多更改陆续到来！

Azure Repos 提供了两种版本控制模型：Git（分布式版本控制系统）和 Team Foundation 版本控制 (TFVC)（集中式版本控制系统）。 本文提供借助 Visual Studio for Mac 使用 TFVC 的概述和起点。

## <a name="requirements"></a>要求

* Visual Studio Community、Professional 或 Enterprise for Mac 版本 7.5 或更高版本。
* Azure DevOps Services 或 Team Foundation Server 2013 及更高版本。
* Azure DevOps Services 或 Team Foundation Server 中的项目，配置为使用 Team Foundation 版本控制。

## <a name="installation"></a>安装

在 Visual Studio for Mac 中，从菜单中选择“Visual Studio”>“扩展”  。 在“库”选项卡中，选择“版本控制”>“适用于 TFS 和 VSTS 的 Team Foundation 版本控制”，然后单击“安装”    ：

![扩展管理器](media/tfvc-install.png)

按照提示安装扩展。 安装后，重启 IDE。

## <a name="updating-the-extension"></a>更新扩展

TFVC 扩展定期更新。 若要访问更新，请从菜单中选择“Visual Studio”>“扩展...”，然后选择“更新”选项卡   。从列表中选择扩展，然后选择“更新”按钮  ：

![显示更新的扩展管理器](media/tfvc-update.png)

选择下一对话框中的“安装”来卸载旧包并安装新包  。

## <a name="using-the-add-in"></a>使用加载项

安装扩展后，选择“版本控制”>“TFS/Azure DevOps”>“从远程存储库打开”菜单项  。

![用于打开扩展的菜单项](media/tfvc-source-control-explorer-devops.png)

选择 VSTS 或 Team Foundation Server 以开始使用，然后选择“继续”  ：

![与服务器连接](media/tfvc-choose-server-type-devops.png)

### <a name="azure-repos-authentication"></a>Azure Repos 身份验证

选择在 Azure Repos 上托管的项目时，系统会提示输入 Microsoft 帐户详细信息：

![与 Azure Repos 连接](media/tfvc-vsts-login.png)

### <a name="tfs-authentication"></a>TFS 身份验证

若要连接到 TFS，请输入服务器详细信息和帐户凭据。 若要使用 NTLM 身份验证，请输入域；若要使用基本身份验证，则留空。 选择“添加服务器”  ：

![登录 TFS 服务器](media/tfvc-login.png)

## <a name="selecting-a-project"></a>选择项目

成功通过身份验证后，可在“在源代码管理中打开”对话框中看到与帐户关联的存储库的列表  ：

![显示项目的“在源代码管理中打开”对话框](media/tfvc-vsts-projects.png)

此对话框分为以下节点：

- Azure DevOps 组织或集合 - 这显示连接到所登录 Microsoft 帐户的所有组织。
- 项目 - 在每个组织或集合中，可以拥有许多项目。 项目中托管源代码、工作项和自动生成。

现在可按项目或组织的名称进行搜索和筛选。

### <a name="adding-a-new-server"></a>添加新服务器

若要将新服务器添加到列表，请在“在源代码管理中打开”对话框中选择“添加主机”按钮   ：

![突出显示的添加按钮，用于将新服务器添加到列表](media/tfvc-add-new-server.png)

从列表中选择提供程序并输入凭据：

![显示源代码管理提供程序的选项的对话框](media/tfvc-add-new-creds-devops.png)

## <a name="creating-a-new-workspace"></a>创建一个新工作区

若要开始使用项目，则需具备“工作区”  。 如果还没有工作区，可通过“在源代码管理中打开”对话框中的“工作区”组合框进行创建   ：

![创建新工作区组合框选项](media/tfvc-create-new-workspace.png)

设置新工作区的名称和本地路径，并选择“创建工作区”  :

![输入新工作区的名称和本地路径](media/tfvc-local-workspace.png)

## <a name="using-the-source-code-explorer"></a>使用源代码资源管理器

创建工作区并映射项目后，则可开始使用“源代码资源管理器”  。

若要打开源代码资源管理器，请选择“版本控制”>“TFS/Azure DevOps”>“源代码管理器”菜单项  。

利用源代码资源管理器可以浏览所有映射的项目及其文件和文件夹。 还可以执行所有基本源代码管理操作，例如：

- 获取最新版本
- 获取特定版本
- 签入和签出文件
- 锁定和解锁文件
- 添加、删除和重命名文件
- 查看历史记录
- 比较更改。

许多这些操作都可以通过项目的上下文操作实现：

![项目的上下文菜单操作](media/tfvc-sourcecode-actions.png)

## <a name="managing-workspaces"></a>管理工作区

如果尚未创建工作区（如[创建工作区](#creating-a-new-workspace)部分所述），则会发现源代码资源管理器是空的：

![空源代码资源管理器](media/tfvc-setup-empty-sce.png)

若要使用本地工作区设置远程项目，请执行以下步骤：

1. 从组合框中选择“服务器”  。
1. 请注意，此时显示“无工作区”，并且本地路径为“未映射”。 选择“未映射”链接，以显示“创建新工作区”对话框   。
1. 为工作区提供一个名称，然后单击“添加工作文件夹”，将项目映射到计算机上的本地文件夹  ：

    ![显示默认选项的“创建新工作区”对话框](media/tfvc-workspace1.png)

1. 选择“$”文件夹，将服务器上的所有项目映射到同一工作区；或选择单个项目，然后单击“确定”  ：

    ![显示所有项目的“浏览文件夹”对话框](media/tfvc-workspace2.png)

1. 在本地计算机上选择希望将项目映射到的位置，然后单击“选择文件夹”  。
1. 选择“确定”，确认新工作区的详细信息后 

    ![添加了工作文件夹的“创建新工作区”对话框](media/tfvc-workspace3.png)

设置工作区后，可通过单击源代码资源管理器中的“管理工作区”按钮来进行更改或将其删除  。

![管理工作区](media/tfvc-workspace4.png)

## <a name="troubleshooting"></a>疑难解答

### <a name="problems-using-basic-authentication"></a>使用基本身份验证的问题

可使用以下选项对服务器进行身份验证：

- Oauth
- Basic
- Ntlm

若要使用基本身份验证，需要在 Azure DevOps Services 中启用“其他身份验证凭据”，具体步骤如下  ：

1. 以所有者身份登录到 Azure DevOps 组织 (https:\//dev.azure.com/{organization}/{project})。

2. 在组织工具栏中，选择齿轮图标，然后选择“策略”  ：

    ![选中的策略设置选项](media/tfvc-auth2.png)

3. 查看应用程序连接设置。 根据安全策略更改这些设置：

    ![选中的策略设置选项](media/tfvc-auth.png)

### <a name="i-do-not-see-anything-in-tfvc"></a>我在 TFVC 中没有看到任何内容

若要在开发计算机上设置 Team Foundation 版本控制 (TFVC)，必须按照[管理工作区](#managing-workspaces)部分所述创建工作区  。

在源代码管理器中，按“管理工作区”按钮  。 按照步骤将项目映射到开发计算机上的文件夹。

### <a name="i-do-not-see-any--all-of-my-projects"></a>我没有看到任何/所有项目

身份验证后，应该可以看到项目列表。 默认情况下，只显示 TFS 项目。 要查看其他类型的项目，请选中“查看所有项目”框。

请记住，只有权限正确，才会显示服务器上的项目。

#### <a name="i-am-getting-the-error-cannot-create-the-workspace-please-try-again"></a>我收到“无法创建工作区， 请重试”错误

尝试[创建新工作区](#creating-a-new-workspace)时，应确保满足以下条件：

- 工作区名称中不可使用无效字符。
- 名称必须少于 64 个字符。
- 任何其他工作区都不能使用本地路径。

## <a name="see-also"></a>请参阅

- [使用 Visual Studio 开发和共享 TFVC 中的代码 (Windows)](/azure/devops/repos/tfvc/share-your-code-in-tfvc-vs)