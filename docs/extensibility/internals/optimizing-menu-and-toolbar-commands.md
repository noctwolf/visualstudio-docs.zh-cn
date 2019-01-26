---
title: 优化菜单和工具栏命令 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands [Visual Studio], menus
- commands [Visual Studio], toolbars
- menus [Visual Studio SDK], commands
- menu commands, implementing
- toolbars [Visual Studio], commands
ms.assetid: 8385f1a6-1e98-4dca-83d2-fcbed7177242
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c68822c2dc640008079b0d518fb5774be9a46ea6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037741"
---
# <a name="optimizing-menu-and-toolbar-commands"></a>优化菜单和工具栏命令
Vspackage 和到其相应命令添加[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]可能会导致很拥挤的 UI。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 提供的方法，帮助最小化 UI 命令混淆。  
  
## <a name="in-this-section"></a>本节内容  
 [提供可用命令](../../extensibility/internals/making-commands-available.md)  
 提供有关最大程度减少排满的通用准则[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]UI 时添加的 Vspackage。  
  
 [放置指南](../../extensibility/internals/command-placement-guidelines.md)  
 提供用于实现命令集的大小根据 VSPackage 的特定准则。  
  
## <a name="related-sections"></a>相关章节  
 [命令、菜单和工具栏](../../extensibility/internals/commands-menus-and-toolbars.md)  
 说明如何创建包含菜单、工具栏和命令组合框的 UI。