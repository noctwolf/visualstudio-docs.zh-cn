---
title: "在防火墙或代理服务器后安装 Visual Studio | Microsoft Docs"
description: 
ms.custom: 
ms.date: 08/01/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs
ms.assetid: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3862c6ed49e00ffa3800cccbedb2b846823418ed
ms.sourcegitcommit: 06cdc1651aa7f45e03d260080da5a623d6258661
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="install-visual-studio-behind-a-firewall-or-proxy-server"></a>在防火墙或代理服务器后安装 Visual Studio

Visual Studio 安装程序从各种域及其下载服务器下载文件。 此页列出了你希望在部署脚本中作为受信任的项列入“白名单”的域 URL。

如果适用于环境，请考虑添加同时使用 HTTP 和 HTTPS 协议的以下域。

## <a name="microsoft-domains"></a>Microsoft 域
| Domain | 目标 |
| ------ | ------- |
| go.microsoft.com | 安装程序 URL 解析 |
| aka.ms | 安装程序 URL 解析 |
| download.visualstudio.microsoft.com | 安装包下载位置 |
| download.microsoft.com | 安装包下载位置 |
| download.visualstudio.com | 安装包下载位置 |
| dl.xamarin.com | 安装包下载位置 |
| visualstudiogallery.msdn.microsoft.com | Visual Studio 扩展下载位置 |
| www.visualstudio.com | 文档位置 |
| docs.microsoft.com | 文档位置 |
| msdn.microsoft.com | 文档位置 |
| www.microsoft.com | 文档位置 |
| *.windows.net | 登录位置 |
| *.microsoftonline.com | 登录位置 |
| *.live.com | 登录位置 |


## <a name="non-microsoft-domains"></a>非 Microsoft 域
| Domain | 安装这些工作负载 |
| ------ | ------- |
| archive.apache.org |  使用 JavaScript 的移动开发 <br />(Cordova) |
| cocos2d-x.org | 使用 C++ 的游戏开发 <br />(Cocos) |
| download.epicgames.com | 使用 C++ 的游戏开发 <br />(Unreal Engine) |
| download.oracle.com | 使用 JavaScript 的移动开发 <br />(Java SDK) <br /><br />使用 .NET 的移动开发 <br />(Java SDK) |
| download.unity3d.com | 使用 Unity 的游戏开发 <br />(Unity) |
| netstorage.unity3d.com | 使用 Unity 的游戏开发 <br /> (Unity) |
| dl.google.com | 使用 JavaScript 的移动开发 <br />（Android SDK 和 NDK，仿真器） <br /><br />使用 .NET 的移动开发 <br />（Android SDK 和 NDK，仿真器） |
| www.incredibuild.com | 使用 C++ 的游戏开发 <br />(IncrediBuild) |
| incredibuildvs2017i.azureedge.net | 使用 C++ 的游戏开发 <br />(IncrediBuild) |
| www.python.org | Python 开发 <br />(Python) <br /><br />数据科学和分析应用程序 <br />(Python) |

## <a name="get-support"></a>获取支持
有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅
* [安装 Visual Studio 2017](install-visual-studio.md)
* [使用命令行参数安装 Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md)
  * [命令行参数示例](command-line-parameter-examples.md)
  * [工作负载和组件 ID 参考](workload-and-component-ids.md)
* [创建基于网络的 Visual Studio 2017 安装](create-a-network-installation-of-visual-studio.md)
  * [安装 Visual Studio 脱机安装所需的证书](install-certificates-for-visual-studio-offline.md)
* [通过响应文件自动执行 Visual Studio 安装](automated-installation-with-response-file.md)
* [在部署 Visual Studio 时自动应用产品密钥](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [为 Visual Studio 2017 企业部署设置默认值](set-defaults-for-enterprise-deployments.md)
* [禁用或移动包缓存](disable-or-move-the-package-cache.md)
* [更新基于网络的 Visual Studio 安装](update-a-network-installation-of-visual-studio.md)
* [控制 Visual Studio 2017 部署的更新](controlling-updates-to-visual-studio-deployments.md)
* [用于检测和管理 Visual Studio 实例的工具](tools-for-managing-visual-studio-instances.md)
