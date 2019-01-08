---
title: 容器的已知问题
description: 详细了解将 Visual Studio 生成工具 2017 安装到 Windows 容器时可能会出现的已知问题。
ms.date: 04/18/2018
ms.technology: vs-acquisition
ms.custom: seodec18
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d817b7d45c23e813a8d3f80e2b74ea860bb8a3cf
ms.sourcegitcommit: 8cdc6e2ad2341f34bd6b02859a7c975daa0c9320
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "53307760"
---
# <a name="known-issues-for-containers"></a>容器的已知问题

向 Docker 容器中安装 Visual Studio 时存在几个问题。

## <a name="windows-container"></a>Windows 容器

将 Visual Studio 生成工具 2017 安装到 Windows 容器时会出现以下已知问题。

* 无法将 Visual Studio 安装到基于映像 microsoft/windowsservercore:10.0.14393.1593 的容器。 标记为 10.0.14393 之前或之后的 Windows 版本的映像应该能正常工作。
* 无法安装 10.0.14393 或更早的 Windows SDK 版本。 无法安装某些程序包，而依赖这些程序包的工作负载也无法正常工作。
* 生成映像时传递 `-m 2GB`（或更多）。 某些工作负载安装时要求内存大于默认的 1 GB。
* 将 Docker 配置为使用大于默认 20 GB 的磁盘。
* 在命令行上传递 `--norestart`。 本文撰写之时，尝试从 Windows 容器内重新启动容器会向主机返回 `ERROR_TOO_MANY_OPEN_FILES`。
* 如果映像直接基于 microsoft/windowsservercore，可能无法正确安装 .NET Framework，且不会指示任何安装错误。 安装完成后，可能无法运行托管代码。 相反，可使映像以 [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) 或更高版本为基础。 例如，在使用 MSBuild 进行生成时可能会看到与以下类似的错误：

  > C:\BuildTools\MSBuild\15.0\bin\Roslyn\Microsoft.CSharp.Core.targets(84,5): error MSB6003:无法运行指定的任务可执行文件“csc.exe”。 无法加载文件或程序集“System.IO.FileSystem, Version=4.0.1.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a”或某个依赖项。 系统找不到指定的文件。

* 无法在 mcr<span></span>.microsoft.com/windows/servercore:1809 或更高版本上安装 VisualStudio2017 版本 15.8 或更早版本（任何产品）。 有关更多信息，请参见 https://aka.ms/setup/containers/servercore1809。

## <a name="build-tools-container"></a>生成工具容器

使用生成工具容器时可能会出现以下已知问题。 要查看问题是否已修复，或者是否有其他已知问题，请访问 https://developercommunity.visualstudio.com。

* 在[某些情况](https://github.com/Microsoft/vstest/issues/940)下，IntelliTrace 在容器内可能无法正常工作。

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>请参阅

* [将生成工具安装到容器](build-tools-container.md)
* [容器的高级示例](advanced-build-tools-container.md)
* [Visual Studio 生成工具 2017 工作负载和组件 ID](workload-component-id-vs-build-tools.md)
