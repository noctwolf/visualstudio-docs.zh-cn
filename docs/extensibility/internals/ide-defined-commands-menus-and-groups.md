---
title: IDE 定义的命令、 菜单和组 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, environment-defined
- .vsct files, environment-defined constants
- command groups, environment-defined
ms.assetid: 86b3af13-7163-48c6-986b-7beeedbc26cc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 727c999e275830260ce83eac3d2d72024e89882b
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602372"
---
# <a name="ide-defined-commands-menus-and-groups"></a>IDE 定义的命令、菜单和组
多个菜单、 命令和命令组已定义以供[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]IDE。 在扩展时，这些命令也已可供你使用[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。

## <a name="finding-environment-defined-commands"></a>查找环境定义的命令
 一组四个.vsct 文件中定义的环境命令：

- SharedCmdDef.vsct

- SharedCmdPlace.vsct

- ShellCmdDef.vsct

- ShellCmdPlace.vsct

  这些文件位于 *\<Visual Studio SDK 安装路径 >* \VisualStudioIntegration\Common\Inc\\。 这些文件提供定义和菜单和组可用于你的 VSPackage 的命令表配置 (.vsct) 文件中作为容器菜单、 组和命令的 Guid。

## <a name="in-this-section"></a>本节内容
- [Visual Studio 菜单中的 GUID 和 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)

 提供的 GUID 和 ID 值的菜单栏上的 Visual Studio 菜单上，以及它们所包含的组。

- [Visual Studio 工具栏中的 GUID 和 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)

 提供的 Visual Studio IDE 中的工具栏和它们所包含的组的 GUID 和 ID 值。

- [Visual Studio 命令中的 GUID 和 ID](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)

 提供了由 Visual Studio IDE 定义的命令 GUID 和 ID 值。

## <a name="see-also"></a>请参阅
- [Visual Studio 命令表格 (.Vsct) 文件](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [用于扩展项目系统的 IDE 定义的命令](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)
- [VSPackage 如何添加用户界面元素](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)