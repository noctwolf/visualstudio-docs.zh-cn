---
title: 用于检测和管理 Visual Studio 实例的工具
description: 了解可用于在客户端计算机上检测和管理 Visual Studio 安装的工具。
ms.date: 08/14/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 85686707-14C0-4860-9B7A-66485D43D241
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1701ff4d17815bc70444fe360ebf1acf61ea2af4
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="tools-for-detecting-and-managing-visual-studio-instances"></a>用于检测和管理 Visual Studio 实例的工具

有几种工具可用于在客户端计算机上检测和管理 Visual Studio 安装。

## <a name="detecting-existing-visual-studio-instances"></a>检测现有 Visual Studio 实例

我们提供了几种工具来帮助你检测和管理在客户端计算机上安装的 Visual Studio 实例：

* [VSWhere](https://github.com/microsoft/vswhere)：一个可执行文件，内置于 Visual Studio 或可单独分发，可帮助查找特定计算机上所有 Visual Studio 实例的位置。
* [VSSetup.PowerShell](https://github.com/microsoft/vssetup.powershell)：使用安装程序配置 API 来标识已安装的 Visual Studio 实例的 PowerShell 脚本。
* [VS-Setup-Samples](https://github.com/microsoft/vs-setup-samples)：展示了如何使用安装程序配置 API 来查询现有安装的 C# 和 C++ 示例。

此外，[安装程序配置 API](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.setup.configuration.aspx) 提供了接口，方便开发者生成自己的实用工具来询问 Visual Studio 实例。

## <a name="using-vswhereexe"></a>使用 vswhere.exe

`vswhere.exe` 自动包含在 Visual Studio 2017 15.2 或更高版本中，也可以从[发布页](https://github.com/Microsoft/vswhere/releases)中下载。 使用 `vswhere -?` 获取有关该工具的帮助信息。 作为示例，此命令显示了 Visual Studio 的所有版本（包括产品和预发行版本的旧版本），并输出 JSON 格式的结果：

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Installer> vswhere.exe -legacy -prerelease -format json
```

>[!TIP]
>有关 Visual Studio 2017 安装的详细信息，请参阅 [Heath Stewart 的博文](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/)。


## <a name="editing-the-registry-for-a-visual-studio-instance"></a>编辑 Visual Studio 实例的注册表

在 Visual Studio 2017 中，注册表设置存储在专用位置中，以便于可以在同一计算机上安装相同版本 Visual Studio 的多个并行实例。

由于这些条目并非存储在全局注册表中，因此需要遵循有关使用注册表编辑器更改注册表设置的特殊说明：

1. 如果有打开的 Visual Studio 2017 实例，请予以关闭。
2. 启动 `regedit.exe`。
3. 选择“`HKEY_LOCAL_MACHINE`”节点。
4. 在 Regedit 主菜单中，依次选择“文件 -> 加载配置单元...”，然后选择专用注册表文件（存储在“AppData\Local”文件夹中）。 例如:
   ```
   %localappdata%\Microsoft\VisualStudio\<config>\privateregistry.bin
   ```

  > [!NOTE]
  > `<config>` 对应于要浏览的 Visual Studio 实例。

系统会提示你输入配置单元名称，这将成为你的独立配置单元的名称。 执行此操作后，应该能够在所创建的独立配置单元下浏览注册表。

> [!IMPORTANT]
> 必须先卸载已创建的独立配置单元，然后才能再次启动 Visual Studio。 为此，请依次选择 Regedit 主菜单中的“文件 -> 卸载配置单元”。 （如果不这样做，文件会一直处于锁定状态，且 Visual Studio 无法启动。）

## <a name="get-support"></a>获取支持

有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：

* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题并找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。 （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

* [Visual Studio 管理员指南](visual-studio-administrator-guide.md)
