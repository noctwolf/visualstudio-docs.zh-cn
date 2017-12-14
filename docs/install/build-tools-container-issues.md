---
title: "容器的已知问题 | Microsoft Docs"
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: 73bf7daf0a09ead0277e8c5c273c275cd2006ed9
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2017
---
# <a name="known-issues-for-containers"></a>容器的已知问题

向 Docker 容器中安装 Visual Studio 时存在几个问题。

## <a name="windows-container"></a>Windows 容器

将 Visual Studio 生成工具 2017 安装到 Windows 容器时会出现以下已知问题。

* 无法将 Visual Studio 安装到基于映像 microsoft/windowsservercore:10.0.14393.1593 的容器。 标记有较旧或较新 Windows 版本的映像应该能正常工作。
* 无法安装低于 10.0.14393 的 Windows SDK 版本。 无法安装某些程序包，而依赖这些程序包的工作负载也无法正常工作。
* 生成映像时必须传递 `-m 2GB`（或更多）。 某些工作负载安装时要求内存大于默认的 1 GB。
* 必须将 Docker 配置为使用大于默认 20 GB 的磁盘。
* 必须在命令行上传递 `--norestart`。 本文撰写之时，尝试从 Windows 容器内重新启动容器会向主机返回 `ERROR_TOO_MANY_OPEN_FILES`。

## <a name="build-tools-container"></a>生成工具容器

使用生成工具容器时可能会出现以下已知问题。 若要查看问题是否已修复，或者是否有其他已知问题，请访问 https://developercommunity.visualstudio.com。

* 在[某些情况](https://github.com/Microsoft/vstest/issues/940)下，IntelliTrace 在容器内可能无法正常工作。

## <a name="get-support"></a>获取支持
有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （此选项需要 [GitHub](https://github.com/) 帐户）。

## <a name="see-also"></a>请参阅

* [将生成工具安装到容器](build-tools-container.md)
* [容器的高级示例](advanced-build-tools-container.md)
