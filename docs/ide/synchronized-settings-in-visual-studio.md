---
title: 同步设置
ms.date: 01/23/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.RoamingSettings
ms.assetid: a3d2ea29-be5d-4012-9820-44b06adbb7dd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 633767e66a4b3d976999574c885a3e6f7a06ddcf
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766124"
---
# <a name="synchronize-visual-studio-settings-across-multiple-computers"></a>跨多台计算机同步 Visual Studio 设置

使用同一个性化帐户在多台计算机上登录 Visual Studio 时，可跨计算机同步设置。

## <a name="synchronized-settings"></a>同步设置

默认情况下，以下设置会进行同步：

- 开发设置。 必须在首次运行 Visual Studio 时选择一组设置，但是可以随时更改选择。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)。

- 用户定义的命令别名。 有关如何定义命令别名的详细信息，请参阅 [Visual Studio 命令别名](../ide/reference/visual-studio-command-aliases.md)。

- “窗口” > “管理窗口布局”页中用户定义的窗口布局。

- “工具” > “选项”页中的以下选项：

   - “主题”和菜单栏大小写设置（位于“环境” > “常规”选项页上）。

   - “环境” > “字体和颜色”选项页上的所有设置。

   - 所有键盘快捷方式（位于“环境” > “键盘”选项页上）。

   - “环境” > “选项卡和窗口”选项页上的所有设置。

   - “环境” > “启动”选项页上的所有设置。

   - “文本编辑器”选项页上的所有设置。

   - “XAML 设计器”选项页上的所有设置。

## <a name="turn-off-synchronized-settings-on-a-particular-computer"></a>关闭特定计算机上的同步设置

默认情况下启用 Visual Studio 的同步设置。 可以通过转到“工具” > “选项” > “环境” > “帐户”页并取消选中“登录到 Visual Studio 时，跨设备同步设置”，关闭计算机上的同步设置。 例如，如果决定不同步计算机“A”上的 Visual Studio 设置，那么计算机“A”上的任何设置更改将不会出现在计算机“B”或计算机“C”上。 计算机“B”和“C”将继续与彼此同步，但不与计算机“A”同步。

## <a name="reset-settings"></a>重置设置

可按照以下步骤将所有设置重置为默认设置的集合：

1. 在 Visual Studio 中，选择“工具” > “导入和导出设置”以打开“导入和导出设置向导”。

1. 在“导入和导出设置向导”中，选择“重置所有设置”，然后选择“下一步”。

   ![在 Visual Studio 中导入和导出设置向导](media/reset-all-settings.png)

1. 在“保存当前设置”页上，选择“是”或“否”，然后选择“下一步”。

1. 在“选择设置的默认集合”页上，选择一个集合，然后选择“完成”。

   ![Visual Studio 中的设置集合](media/settings-collections.png)

1. 在“重置完成”页上，选择“关闭”。

## <a name="synchronize-settings-across-visual-studio-family-products-and-editions"></a>在 Visual Studio 系列产品和版本之间同步设置

可以在 Visual Studio 的任何版本（包括 Community 版本）之间同步设置。 Visual Studio 系列产品之间的设置也是同步的。 但是，这些系列产品中的每一个都可能具有它自己与 Visual Studio 不共享的设置。 例如，特定于计算机“A”上的某种产品的设置将与计算机“B”上的另一种产品共享，但不与计算机“A”或“B”上的 Visual Studio 共享。

## <a name="side-by-side-synchronized-settings"></a>并排同步设置

在 Visual Studio 2017 版本 15.3 及更高版本中，不会在不同的 Visual Studio 2017 并行安装之间共享某些设置（如工具窗口布局）。 %userprofile%\Documents\Visual Studio 2017\Settings 中的 CurrentSettings.vssettings 文件位于特定于安装的文件夹中，该文件夹类似于 %localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx\Settings。

> [!NOTE]
> 要使用新的特定于安装的设置，请进行全新安装。 将现有 Visual Studio 2017 安装升级到最新更新时，它会使用现有共享位置。

如果现在已拥有 Visual Studio 2017 的并行安装，并希望使用特定于安装的新设置文件位置，请执行以下步骤：

1. 升级到 Visual Studio 2017 版本 15.3 或更高版本。

1. 使用“导入\导出”设置向导将所有现有设置导出到“%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx”文件夹之外的某个位置。

1. 打开已安装的升级后 Visual Studio 的 VS 2017 开发者命令提示符，并运行 `devenv /resetuserdata`。

1. 启动 Visual Studio，并从导出的设置文件中导入保存的设置。

## <a name="see-also"></a>请参阅

[个性化 IDE](../ide/personalizing-the-visual-studio-ide.md)
