---
title: 将 Visual Studio 生成工具安装到容器
titleSuffix: ''
description: 了解如何将 Visual Studio 生成工具安装到 Windows 容器，以支持持续集成和持续交付 (CI/CD) 工作流。
ms.date: 04/18/2018
ms.custom: seodec18
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: d5c038e2-e70d-411e-950c-8a54917b578a
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3e98ff7f21ab7620092f2b535f17c55ab4d584b7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53946628"
---
# <a name="install-build-tools-into-a-container"></a>将生成工具安装到容器

可以将 Visual Studio 生成工具安装到 Windows 容器，用于支持持续集成和持续交付 (CI/CD) 工作流。 本文将指导你完成所需的 Docker 配置更改以及可以在容器中安装的[工作负荷和组件](workload-component-id-vs-build-tools.md)。

对于包装不仅可以在 CI/CD 服务器环境中使用，而且可以用于开发环境的一致的生成系统，[容器](https://www.docker.com/what-container)是一种好方法。 例如，可以将源代码装载到要由自定义环境生成的容器中，同时继续使用 Visual Studio 或其他工具编写代码。 如果 CI/CD 工作流使用相同容器映像，则可以确信代码会以一致的方式生成。 还可以使用容器来实现运行时一致性，这对于将多个容器与业务流程系统一起使用的微服务十分常见，但不在本文的讨论范围内。

如果 Visual Studio 生成工具没有生成源代码所需的内容，则可以将这些相同步骤用于其他 Visual Studio 产品。 但是请注意，Windows 容器不支持交互用户界面，因此所有命令都必须自动执行。

## <a name="overview"></a>概述

使用 [Docker](https://www.docker.com/what-docker) 可创建映像，而通过映像可以创建生成源代码的容器。 示例 Dockerfile 安装最新 Visual Studio 15 生成工具 2017 以及通常用于生成源代码的一些其他有用程序。 可以进一步修改自己的 Dockerfile 以包括其他工具和脚本，来运行测试、发布生成输出等。

如果已安装用于 Windows 的 Docker，则可以跳到步骤 3。

## <a name="step-1-enable-hyper-v"></a>步骤 1。 启用 Hyper-V

默认情况下不会启用 Hyper-V。 必须启用它才能启动用于 Windows 的 Docker，因为当前只对 Windows 10 支持 Hyper-V 隔离。

* [在 Windows 10 上启用 Hyper-V](https://docs.microsoft.com/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v)
* [在 Windows Server 2016 上启用 Hyper-V](https://docs.microsoft.com/windows-server/virtualization/hyper-v/get-started/install-the-hyper-v-role-on-windows-server)

> [!NOTE]
> 必须在计算机上启用虚拟化。 默认情况下通常会启用它；但是，如果 Hyper-V 安装失败，请参阅系统文档以了解如何启用虚拟化。

## <a name="step-2-install-docker-for-windows"></a>步骤 2。 安装用于 Windows 的 Docker

如果使用 Windows 10，则可以[下载并安装 Docker 社区版](https://docs.docker.com/docker-for-windows/install)。 如果使用 Windows Server 2016，请遵循[安装 Docker 企业版的说明](https://docs.docker.com/install/windows/docker-ee)。

## <a name="step-3-switch-to-windows-containers"></a>步骤 3。 切换到 Windows 容器

只能在 Windows 上安装生成工具 2017，这要求[切换到 Windows 容器](https://docs.docker.com/docker-for-windows/#getting-started-with-windows-containers)。 Windows 10 上的 Windows 容器仅支持 [Hyper-V 隔离](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container)，而 Windows Server 2016 上的 Windows 容器同时支持 Hyper-V 和进程隔离。

## <a name="step-4-expand-maximum-container-disk-size"></a>步骤 4。 扩展最大容器磁盘大小

Visual Studio 生成工具（在更大程度上是 Visual Studio）需要大量磁盘空间以用于安装的所有工具。 即使示例 Dockerfile 禁用包缓存，仍必须增加容器映像的磁盘大小以容纳所需空间。 当前在 Windows 上，只能通过更改 Docker 配置来增加磁盘大小。

**在 Windows 10 上**：

1. [右键单击系统托盘中的“用于 Windows 的 Docker”图标](https://docs.docker.com/docker-for-windows/#docker-settings)，再单击“设置”。
2. [单击守护程序](https://docs.docker.com/docker-for-windows/#docker-daemon)部分。
3. [将“基本”](https://docs.docker.com/docker-for-windows/#edit-the-daemon-configuration-file)按钮切换为“高级”。
4. 添加以下 JSON 数组属性以将磁盘空间增大到 120 GB（足以在占用空间增多的情况下用于生成工具）。

   ```json
   {
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

   此属性会添加到你已拥有的任何内容。 例如，将这些更改应用于默认守护程序配置文件之后，你现在应看到：

   ```json
   {
     "registry-mirrors": [],
     "insecure-registries": [],
     "debug": true,
     "experimental": true,
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

5. 单击“应用”。

**在 Windows Server 2016 上**：

1. 停止“docker”服务：

   ```shell
   sc.exe stop docker
   ```

2. 在提升的命令提示符处，编辑“%ProgramData%\Docker\config\daemon.json”（或是指定为 `dockerd --config-file` 的任何内容）。
3. 添加以下 JSON 数组属性以将磁盘空间增大到 120 GB（足以在占用空间增多的情况下用于生成工具）。

   ```json
   {
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

   此属性会添加到你已拥有的任何内容。
4. 保存并关闭文件。
5. 启动“docker”服务：

   ```shell
   sc.exe start docker
   ```

## <a name="step-5-create-and-build-the-dockerfile"></a>步骤 5。 创建和生成 Dockerfile

将下面的示例 Dockerfile 保存为磁盘上的新文件。 如果该文件仅仅命名为“Dockerfile”，则默认情况下会识别它。

> [!WARNING]
> 此示例 Dockerfile 只排除无法安装到容器的较旧 Windows SDK。 较旧版本会导致生成命令失败。

1. 打开命令提示。
2. 创建新目录（推荐）：

   ```shell
   mkdir C:\BuildTools
   ```

3. 将目录更改为此新目录：

   ```shell
   cd C:\BuildTools
   ```

3. 将以下内容保存到 C:\BuildTools\Dockerfile。

   ```dockerfile
   # escape=`

   # Use the latest Windows Server Core image with .NET Framework 4.7.1.
   FROM microsoft/dotnet-framework:4.7.1

   # Restore the default Windows shell for correct batch processing below.
   SHELL ["cmd", "/S", "/C"]

   # Download the Build Tools bootstrapper.
   ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe

   # Install Build Tools excluding workloads and components with known issues.
   RUN C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
       --installPath C:\BuildTools `
       --all `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
       --remove Microsoft.VisualStudio.Component.Windows81SDK `
    || IF "%ERRORLEVEL%"=="3010" EXIT 0

   # Start developer command prompt with any other commands specified.
   ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

   # Default to PowerShell if no other command specified.
   CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
   ```

   > [!WARNING]
   > 如果映像直接基于 microsoft/windowsservercore，可能无法正确安装 .NET Framework，且不会指示任何安装错误。 安装完成后，可能无法运行托管代码。 相反，可使映像以 [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) 或更高版本为基础。 此外请注意，标记为 4.7.1 或更高版本的映像可能使用 PowerShell 作为默认 `SHELL`，这将导致 `RUN` 和 `ENTRYPOINT` 说明失败。
   >
   > Visual Studio 2017 版本 15.8 或更高版本（任何产品）无法在 mcr<span></span>.microsoft\.com\/windows\/servercore:1809 或更高版本上正常安装。 不显示任何错误信息。
   >
   > 有关详细信息，请参阅[容器的已知问题](build-tools-container-issues.md)。

4. 从该目录处运行以下命令。

   ```shell
   docker build -t buildtools2017:latest -m 2GB .
   ```

   此命令使用 2 GB 内存在当前目录中生成 Dockerfile。 安装某些工作负载后，默认值 1 GB 会不够用；你有可能只使用 1 GB 内存进行生成，具体取决于生成环境。

   最终映像带有标记“buildtools2017:latest”，因此你可以在作为“buildtools2017”的容器中轻松运行它因为如果未指定任何标记，则默认情况下使用“latest”标记。 如果要在更[高级的方案](advanced-build-tools-container.md)中使用特定版本的 Visual Studio 15 生成工具 2017加，则你可以改为使用特定 Visual Studio 生成号以及“latest”来标记容器，因此容器可以按一致方式使用特定版本。

## <a name="step-6-using-the-built-image"></a>步骤 6。 使用生成的映像

现在已创建了映像，可以在容器中运行它以进行交互式自动生成。 该示例使用开发人员命令提示，因此已配置了 PATH 和其他环境变量。

1. 打开命令提示。
2. 运行容器以启动 PowerShell 环境（设置了所有开发人员环境变量）：

   ```shell
   docker run -it buildtools2017
   ```

若要将此映像用于 CI/CD 工作流，可以将它发布到自己的 [Azure 容器注册表](https://azure.microsoft.com/services/container-registry)或其他内部 [Docker 注册表](https://docs.docker.com/registry/deploying)，以便服务器只需拉取它即可。

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>请参阅

* [容器的高级示例](advanced-build-tools-container.md)
* [容器的已知问题](build-tools-container-issues.md)
* [Visual Studio 生成工具 2017 工作负载和组件 ID](workload-component-id-vs-build-tools.md)
