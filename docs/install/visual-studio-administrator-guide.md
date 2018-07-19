---
title: Visual Studio 管理员指南
description: 详细了解如何在企业环境中部署 Visual Studio。
ms.custom: ''
ms.date: 05/29/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 59424cdb93d8c664740ddf1d9865ba41044eb72e
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "36283072"
---
# <a name="visual-studio-2017-administrator-guide"></a>Visual Studio 2017 管理员指南

在企业环境中，系统管理员通常会从网络共享或通过使用系统管理软件向最终用户部署安装。 为了支持企业部署，我们精心设计了 Visual Studio 安装程序引擎，以便系统管理员可以创建网络安装位置、预配置安装默认值、在安装过程中部署产品密钥以及管理成功推出的产品更新。 本管理员指南通过各种情境，提供有关在网络环境中进行企业部署的指导。

## <a name="deploy-visual-studio-2017-in-an-enterprise-environment"></a>在企业环境中部署 Visual Studio 2017

只要每台目标计算机满足[最低安装要求](/visualstudio/productinfo/vs2017-system-requirements-vs)，就可以将 Visual Studio 2017 部署到客户端工作站。 无论是通过 System Center 等软件还是通过批处理文件进行部署，通常都需要完成以下步骤：

1. 在网络位置上[创建包含 Visual Studio 产品文件的网络共享](create-a-network-installation-of-visual-studio.md)。

2. [选择要安装的工作负载和组件](workload-and-component-ids.md)。

3. [创建包含默认安装选项的响应文件](automated-installation-with-response-file.md)。 或者，[生成安装脚本](use-command-line-parameters-to-install-visual-studio.md)，使用命令行参数来控制安装。

4. （可选）[应用批量许可证产品密钥](automatically-apply-product-keys-when-deploying-visual-studio.md)作为安装脚本的一部分，这样用户便无需单独激活软件。

5. 将网络布局更新为[控制何时向最终用户提供产品更新](controlling-updates-to-visual-studio-deployments.md)。

6. （可选）将注册表项设置为[控制在客户端工作站上缓存什么内容](set-defaults-for-enterprise-deployments.md)。

7. 使用选定的部署技术，在目标开发者工作站上执行前述步骤中生成的脚本。

8. 定期运行第 1 步中的命令来添加更新后的组件，使用 Visual Studio [最新更新刷新网络位置](update-a-network-installation-of-visual-studio.md)。

> [!IMPORTANT]
> 请注意，从网络共享进行安装会“记住”它们的源位置。 这意味着客户端计算机的修复可能需要返回最初从中安装客户端的网络共享。 请仔细选择网络位置，使其符合在组织中运行的 Visual Studio 2017 客户端的预期生存期。

## <a name="use-visual-studio-tools"></a>使用 Visual Studio 工具

我们提供了几种工具来帮助你在客户端计算机上[检测和管理安装的 Visual Studio 实例](tools-for-managing-visual-studio-instances.md)。

> [!TIP]
> 除了管理员指南中的文档外，[Heath Stewart 的博客](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/)也是不错的 Visual Studio 2017 安装程序参考信息源。

## <a name="specify-customer-feedback-settings"></a>指定客户反馈设置

默认情况下，Visual Studio 安装会启用客户反馈。 启用“组策略”时，可以将 Visual Studio 配置为在个人计算机上禁用客户反馈。 为此，请在以下键上设置基于注册表的策略：

HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\SQM

Entry = OptIn

Value = (DWORD)
* 0 为选择禁用
* 1 为选择启用

有关客户反馈设置的详细信息，请参阅 [Visual Studio 客户体验改善计划](../ide/visual-studio-experience-improvement-program.md)页。

## <a name="get-support"></a>获取支持

有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://visualstudio.microsoft.com/vs/support/#talktous)。

下面是另外几个支持选项：

* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题并找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。 （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

* [安装 Visual Studio 2017](install-visual-studio.md)
* [使用命令行参数安装 Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md)
  * [命令行参数示例](command-line-parameter-examples.md)
  * [工作负载和组件 ID 参考](workload-and-component-ids.md)
* [创建基于网络的 Visual Studio 安装](create-a-network-installation-of-visual-studio.md)
  * [安装 Visual Studio 脱机安装所需的证书](install-certificates-for-visual-studio-offline.md)
* [通过响应文件自动执行 Visual Studio](automated-installation-with-response-file.md)
* [在部署 Visual Studio 时自动应用产品密钥](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [为 Visual Studio 企业部署设置默认值](set-defaults-for-enterprise-deployments.md)
* [禁用或移动包缓存](disable-or-move-the-package-cache.md)
* [更新基于网络的 Visual Studio 安装](update-a-network-installation-of-visual-studio.md)
* [控制 Visual Studio 部署的更新](controlling-updates-to-visual-studio-deployments.md)
* [用于检测和管理 Visual Studio 实例的工具](tools-for-managing-visual-studio-instances.md)
