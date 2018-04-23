---
title: 优化菜单和工具栏命令 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 92072668f96a69a0dc5ff78839b54fa7ecc656bd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="optimizing-menu-and-toolbar-commands"></a>优化菜单和工具栏命令
添加 Vspackage 和到其相应命令[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]可能会导致拥挤的 UI。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 提供方法来帮助减少 UI 命令混淆。  
  
## <a name="in-this-section"></a>本节内容  
 [提供可用命令](../../extensibility/internals/making-commands-available.md)  
 尽量减少的围提供一般准则[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]UI 添加 Vspackage 时。  
  
 [放置准则](../../extensibility/internals/command-placement-guidelines.md)  
 提供用于实现根据命令集的大小 VSPackage 的特定准则。  
  
## <a name="related-sections"></a>相关章节  
 [命令、菜单和工具栏](../../extensibility/internals/commands-menus-and-toolbars.md)  
 说明如何创建包含菜单、工具栏和命令组合框的 UI。