---
title: “选项”对话框 ->“环境”->“区域设置”
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.InternationalSettings
- VS.ToolsOptionsPages.Environment.International_Settings
- VS.Environment.International Settings
helpviewer_keywords:
- International Settings dialog box
- languages, environment settings
- Options dialog box, international settings
- languages, specifying default
ms.assetid: e3a8815c-6995-4099-8e88-34f91fad55b2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1609f33230942c2f5d026eb072e3e85860137d4b
ms.sourcegitcommit: 1abb9cf4c3ccb90e3481ea8079272c98aad12875
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2018
ms.locfileid: "50143146"
---
# <a name="international-settings-environment-options-dialog-box"></a>“选项”对话框 ->“环境”->“区域设置”

当你的计算机上安装有多个语言版本的集成开发环境 (IDE) 时，可通过国际设置页面更改默认语言。 要访问此对话框，可从“工具”菜单中选择“选项”，然后从“环境”文件夹中选择“区域设置”。 如果此页未出现在列表中，请在“选项”对话框中选择“显示所有设置”。

> [!NOTE]
> 对话框中的可用选项以及显示的菜单命令的名称和位置可能与“帮助”中的描述不同，具体取决于您的当前设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)。

 **语言**列出已安装产品语言版本的可用语言。 除非你的计算机上安装了多个语言版本，否则此选项不可用。 如果产品的多个语言或产品的混合语言安装可共享环境，则将语言选项更改为“与 Microsoft Windows 相同”。

> [!CAUTION]
> 在安装了多个语言的系统中，Visual C++ 生成工具（cl.exe、link.exe、nmake.exe、bscmake.exe 和相关文件）不受此设置的影响。 这些工具使用上次安装的语言版本。 以前安装的语言版本的工具将被覆盖，因为 Visual C++ 生成工具不使用附属 DLL 模型。

## <a name="see-also"></a>请参阅

- [安装语言包](../../install/install-visual-studio.md#step-6---install-language-packs-optional)
- [“选项”对话框 ->“环境”](../../ide/reference/environment-options-dialog-box.md)