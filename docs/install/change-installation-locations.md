---
title: 更改 Visual Studio 2017 中的安装位置
description: 了解如何通过将下载缓存、共享组件、SDK 和工具的位置更改到不同的驱动器以减少系统驱动器上的安装痕迹。
ms.date: 05/07/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- change installation locations for Visual Studio
- move installation files to different drives
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eef4f8b66da517e471a25bb36e777f6cc343b0a3
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "33995775"
---
# <a name="change-the-installation-locations-in-visual-studio-2017"></a>更改 Visual Studio 2017 中的安装位置

**15.7 版中的新增功能**：可通过将下载缓存、共享组件、SDK 和工具移动到不同的驱动器减少系统驱动器上的安装痕迹。

操作方法如下。

1. 安装 Visual Studio 时，选择“安装选项”选项卡。

  ![Visual Studio 2017 - 更改安装位置](media/installation-options-by-location.png "更改安装位置")

  > [!IMPORTANT]
  > 如果暂停安装并在稍后继续安装，Visual Studio 会从中断处继续安装。 换言之，安装进度适用于余下需要下载和安装的内容，并且不会从以前的计数开始。

2. 在“Visual Studio IDE”部分中，接受默认值。 这将安装核心产品，并包含特定于此 Visual Studio 版本的文件。

 > [!IMPORTANT]
 > 如果系统驱动器是固态硬盘 (SSD)，这就是我们建议用户接受系统驱动器上默认位置的原因：使用 Visual Studio 进行开发时，会从大量文件中读取数据或将数据写入到其中，这会增加磁盘 I/O 活动。  最好选择最快的驱动器来处理负载。

2. 在“下载缓存”部分，决定是否保留下载缓存，然后相应地选中或取消选中“保留下载缓存”。 <br><br>如果决定不保留下载缓存，则仅临时使用该位置。 同样，此操作将不会影响或删除以前安装的文件。 （若要清除所有安装包，必须单独修改以前的安装。）

3. 在“下载缓存”部分，指定要在其中存储安装文件和清单的驱动器。 <br><br>例如，如果选择“使用 C++ 的桌面开发”工作负载，系统驱动器上临时需要的大小为 1.58 GB，安装完成后即会释放。

 > [!NOTE]
 > 首先将文件下载到系统驱动器上的临时文件夹，并在 Visual Studio 验证后再将其删除，然后将其移动到下载缓存文件夹。 如果选择将下载缓存保留到另一个驱动器，则 Visual Studio 仍需要与系统驱动器上的下载缓存大小相当的磁盘空间。
 > [!IMPORTANT]
 > 该位置在首次安装时进行设置，并且之后无法从安装程序 UI 中更改。 相反，必须[使用命令行参数](use-command-line-parameters-to-install-visual-studio.md)移动下载缓存

4. 在“共享组件、工具和 SDK”部分，指定要在其中存储由 Visual Studio 并行安装共享的文件的驱动器。 使 Visual Studio 安装程序更改其安装位置的 SDK 和工具也存储在该目录中。

 > [!NOTE]
 > 有些工具和 SDK 在其可以安装的位置具有不同的规则。 即使选择另一个位置，这些工具和 SDK 仍将安装在系统驱动器上。

## <a name="get-support"></a>获取支持

有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页获得帮助。 还可以通过[实时聊天](https://www.visualstudio.com/vs/support/#talktous)（仅限英语）联系我们，获得安装帮助；有关详细信息，请参阅 [Visual Studio“联系我们”页面](https://www.visualstudio.com/vs/support/#talktous)。

下面是可供选择的另外几个支持渠道：

* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题并找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。 （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

* [安装 Visual Studio 2017](install-visual-studio.md)
* [更新 Visual Studio 2017](update-visual-studio.md)
* [修改 Visual Studio 2027](update-visual-studio.md)
* [卸载 Visual Studio 2017](uninstall-visual-studio.md)
