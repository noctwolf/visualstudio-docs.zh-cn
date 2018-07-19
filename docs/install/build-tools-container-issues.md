---
title: 容器的已知问题
description: 详细了解将 Visual Studio 生成工具 2017 安装到 Windows 容器时可能会出现的已知问题。
ms.custom: ''
ms.date: 04/18/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 06da94f4f2920aa7ce87822482a762a1451e9acb
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282491"
---
# <a name="known-issues-for-containers"></a>容器的已知问题

向 Docker 容器中安装 Visual Studio 时存在几个问题。

## <a name="windows-container"></a>Windows 容器

将 Visual Studio 生成工具 2017 安装到 Windows 容器时会出现以下已知问题。

* 无法将 Visual Studio 安装到基于映像 microsoft/windowsservercore:10.0.14393.1593 的容器。 标记有较旧或较新 Windows 版本的映像应该能正常工作。
* 无法安装低于 10.0.14393 的 Windows SDK 版本。 无法安装某些程序包，而依赖这些程序包的工作负载也无法正常工作。
* 生成映像时传递 `-m 2GB`（或更多）。 某些工作负载安装时要求内存大于默认的 1 GB。
* 将 Docker 配置为使用大于默认 20 GB 的磁盘。
* 在命令行上传递 `--norestart`。 本文撰写之时，尝试从 Windows 容器内重新启动容器会向主机返回 `ERROR_TOO_MANY_OPEN_FILES`。
* 如果映像直接基于 microsoft/windowsservercore，可能无法正确安装 .NET Framework，且不会指示任何安装错误。 安装完成后，可能无法运行托管代码。 相反，可使映像以 [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) 或更高版本为基础。 例如，在使用 MSBuild 进行生成时可能会看到与以下类似的错误：

  > C:\BuildTools\MSBuild\15.0\bin\Roslyn\Microsoft.CSharp.Core.targets(84,5)：错误 MSB6003：无法运行指定的任务可执行文件“csc.exe”。 无法加载文件或程序集“System.IO.FileSystem, Version=4.0.1.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a”或某个依赖项。 系统找不到指定的文件。

## <a name="build-tools-container"></a>生成工具容器

使用生成工具容器时可能会出现以下已知问题。 要查看问题是否已修复，或者是否有其他已知问题，请访问 https://developercommunity.visualstudio.com。

* 在[某些情况](https://github.com/Microsoft/vstest/issues/940)下，IntelliTrace 在容器内可能无法正常工作。

## <a name="get-support"></a>获取支持

有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://visualstudio.microsoft.com/vs/support/#talktous)。

下面是另外几个支持选项：

* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题并找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。 （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

* [将生成工具安装到容器](build-tools-container.md)
* [容器的高级示例](advanced-build-tools-container.md)
* [Visual Studio 生成工具 2017 工作负载和组件 ID](workload-component-id-vs-build-tools.md)
