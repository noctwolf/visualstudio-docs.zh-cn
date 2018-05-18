---
title: Visual Studio 安装的命令行参数示例
description: 自定义这些示例，以创建自己的 Visual Studio 命令行安装。
ms.date: 05/07/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 837F31AA-F121-46e9-9996-F8BCE768E579
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 96fee1d5174115d95718fd9468b2b5770275ae99
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="command-line-parameter-examples-for-visual-studio-2017-installation"></a>Visual Studio 2017 安装命令行参数示例

为了说明如何[使用命令行参数来安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md)，本文介绍了多个示例，你可以根据自己的需求自定义这些示例。

在每个示例中，`vs_enterprise.exe`、`vs_professional.exe` 和 `vs_community.exe` 表示 Visual Studio 安装引导程序的相应版本，这是启动下载过程的小型（大约 1 MB）文件。 若要使用其他版本，请用相应的安装引导程序名称进行替换。

> [!NOTE]
> 所有命令都需要进行管理提升，如果没有通过提升的提示符启动进程，将显示用户帐户控制提示。
>
> [!NOTE]
>  可以在命令行末尾使用 `^` 字符，将多行连接到一个命令中。 也可以直接在一行中编写这些代码行。 在 PowerShell 中，等效字符为反引号 (`` ` ``)。

## <a name="using---installpath"></a>Using --installPath

* 安装 Visual Studio 的最小实例，不显示任何交互式提示，但显示进度：

 ```cmd
 vs_enterprise.exe --installPath C:\minVS ^
   --add Microsoft.VisualStudio.Workload.CoreEditor ^
   --passive --norestart
 ```

* 使用命令行更新 Visual Studio 实例（不显示任何交互式提示，但显示进度）：

 ```cmd
 vs_enterprise.exe --update --quiet --wait
 vs_enterprise.exe update --wait --passive --norestart --installPath "C:\installPathVS"
 ```

 > [!NOTE]
 > 这两个命令都是必需的。 第一个命令用于更新 Visual Studio 安装程序。 第二个命令用于更新 Visual Studio 实例。 为了避免看到“用户帐户控制”对话框，请以管理员身份运行命令提示符。

* 无提示安装包含法语语言包的 Visual Studio 桌面实例，仅在产品安装后才返回值。

 ```cmd
 vs_enterprise.exe --installPath C:\desktopVS ^
   --addProductLang fr-FR ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --includeRecommended --quiet --wait
 ```

 > [!NOTE]
 > `--wait` 参数旨在用于批处理文件。 在批处理文件中，只有在安装完成后，才会继续执行下一个命令。 `%ERRORLEVEL%` 环境变量包含命令的返回值，如[使用命令行参数安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md) 页面所述。

## <a name="using---layout"></a>Using --layout

* 下载 Visual Studio 核心编辑器（最起码的 Visual Studio 配置）。 仅包括英语语言包：

 ```cmd
 vs_community.exe --layout C:\VS2017
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.CoreEditor
 ```

* 下载 .NET 桌面和 .NET Web 工作负载，以及所有推荐组件和 GitHub 扩展。 仅包括英语语言包：

 ```cmd
 vs_community.exe --layout C:\VS2017 ^
   --lang en-US ^
   --add Microsoft.VisualStudio.Workload.NetWeb ^
   --add Microsoft.VisualStudio.Workload.ManagedDesktop ^
   --add Component.GitHub.VisualStudio ^
   --includeRecommended
 ```

## <a name="using---includerecommended"></a>Using --includeRecommended

* 启动交互式安装 Visual Studio 2017 Enterprise 版本中的所有工作负载和组件：

 ```cmd
 vs_enterprise.exe --all --includeRecommended --includeOptional
 ```

* 借助 Node.js 开发支持，在已安装 Visual Studio 2017 Community 版本的计算机上安装 Visual Studio 2017 Professional 的第二个命名实例：

 ```cmd
 vs_professional.exe --installPath C:\VSforNode ^
   --add Microsoft.VisualStudio.Workload.Node --includeRecommended --nickname VSforNode
 ```

## <a name="using---remove"></a>Using --remove

* 从默认安装的 Visual Studio 实例中删除分析工具组件：

 ```cmd
 vs_enterprise.exe modify ^
   --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" ^
   --remove Microsoft.VisualStudio.Component.DiagnosticTools ^
   --passive
 ```

## <a name="using---path"></a>Using --path

这些命令行参数是 15.7 版中的新内容。 有关这些参数的详细信息，请参阅[使用命令行参数安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md) 页。

* 使用安装、缓存和共享路径：

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path cache="C:\VS\cache" --path shared="C:\VS\shared"`

* 仅使用安装和缓存路径：

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path cache="C:\VS\cache"`

* 仅使用安装和共享路径：

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS" --path shared="C:\VS\shared"`

* 仅使用安装路径：

 `vs_enterprise.exe --add Microsoft.VisualStudio.Workload.CoreEditor --path install="C:\VS"`

## <a name="get-support"></a>获取支持

有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：

* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题并找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。 （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

* [Visual Studio 管理员指南](visual-studio-administrator-guide.md)
* [使用命令行参数安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
* [创建 Visual Studio 2017 的脱机安装](create-an-offline-installation-of-visual-studio.md)
