---
title: 优化菜单和工具栏命令 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- commands [Visual Studio], menus
- commands [Visual Studio], toolbars
- menus [Visual Studio SDK], commands
- menu commands, implementing
- toolbars [Visual Studio], commands
ms.assetid: 8385f1a6-1e98-4dca-83d2-fcbed7177242
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5e9ba18b203a7ccd7fa6384bf4f23cb888286035
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481295"
---
# <a name="optimizing-menu-and-toolbar-commands"></a>优化菜单和工具栏命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[优化菜单和工具栏命令](https://docs.microsoft.com/visualstudio/extensibility/internals/optimizing-menu-and-toolbar-commands)。  
  
Vspackage 和到其相应命令添加[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]可能会导致很拥挤的 UI。 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 提供的方法，帮助最小化 UI 命令混淆。  
  
## <a name="in-this-section"></a>本节内容  
 [提供可用命令](../../extensibility/internals/making-commands-available.md)  
 提供有关最大程度减少排满的通用准则[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]UI 时添加的 Vspackage。  
  
 [放置指南](../../extensibility/internals/command-placement-guidelines.md)  
 提供用于实现命令集的大小根据 VSPackage 的特定准则。  
  
## <a name="related-sections"></a>相关章节  
 [命令、菜单和工具栏](../../extensibility/internals/commands-menus-and-toolbars.md)  
 说明如何创建包含菜单、工具栏和命令组合框的 UI。

