---
title: 部署层模型扩展
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, deploying extensions
- layer models, deploying extensions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: dace2a3de8e61a92672442adbf77199232c76e12
ms.sourcegitcommit: 3dd15e019cba7d35dbabc1aa3bf55842a59f5278
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46370908"
---
# <a name="deploy-a-layer-model-extension"></a>部署层模型扩展

其他 Visual Studio 用户可通过使用 Visual Studio 安装你创建的层建模扩展。

## <a name="install-your-extension"></a>安装扩展

将你的扩展编译为可在其他计算机上安装的 VSIX 文件。 你也可以将其安装到开发计算机，确保该扩展在 Visual Studio 的主实例中可用。

### <a name="to-install-the-extension"></a>安装扩展

1.  中包含的项目**source.vsix.manifest**，打开**bin\\ \*** 在文件资源管理器。

2.  复制 **\*.vsix**到要安装扩展的计算机的文件。

3.  在目标计算机的 Windows 资源管理器中，双击 *.vsix 文件。

     VSIX 安装程序将打开。

### <a name="to-uninstall-the-extension"></a>卸载扩展

1.  在 Visual Studio 中，在**工具**菜单上，单击**扩展和更新**。

2.  单击扩展的名称，然后单击**卸载**。

## <a name="install-an-extension-on-team-foundation-server"></a>Team Foundation Server 上安装扩展

Team Foundation Server 服务器通常没有安装 Visual Studio，并因此不能通过双击安装 VSIX。 必须手动安装扩展。

### <a name="to-install-your-layer-extension-on-a-team-foundation-server-server"></a>若要在 Team Foundation Server 服务器上安装层扩展

1.  复制 **.vsix**文件从开发计算机复制到 Team Foundation Server (TFS) 计算机。

     将 VSIX 文件置于下列位置之一：

    -   为所有用户和服务安装：

         %ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft

    -   若要安装仅适用于运行生成的网络服务：

         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

    -   如果已配置要在以特定用户的交互模式下运行的生成，则可以安装仅为该用户：

         %LocalAppData%\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

2.  将各个 VSIX 文件展开至相同位置的文件夹中：

    1.  更改文件扩展名，从 **.vsix**到 **.zip**。

    2.  将 .zip 文件中的内容提取到一个文件夹中。

    3.  删除 .zip 文件。

3.  重新启动 TFS。
