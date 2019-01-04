---
title: 命令处理 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - command handling
ms.assetid: 78f67d92-77f7-45cb-ad75-6e3346379cc3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4198cf6bbed2d8f6172872e4f98f1edb4749e7d7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53926304"
---
# <a name="command-handling"></a>命令处理
你的编辑器可以定义新的命令。 在菜单中，在工具栏上，或在上下文菜单中，通常显示命令。  
  
 有关定义命令和菜单的详细信息，请参阅[命令、 菜单和工具栏](../extensibility/internals/commands-menus-and-toolbars.md)。  
  
 语言服务可以控制哪些上下文菜单显示在编辑器中，通过截获<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>枚举。 或者，可以控制在每个标记的基础上的上下文菜单。 有关详细信息，请参阅[语言服务筛选器的重要命令](../extensibility/internals/important-commands-for-language-service-filters.md)。  
  
## <a name="add-commands-to-the-editor-context-menu"></a>将命令添加到编辑器上下文菜单  
 若要添加到上下文菜单命令，必须首先定义一组属于特定组的菜单命令。 下面的示例取自 *.vsct*文件作为本演练的一部分生成[演练：将功能添加到自定义编辑器](../extensibility/walkthrough-adding-features-to-a-custom-editor.md):  
  
 \<菜单 guid ="guidCustomEditorCmdSet"id ="IDMX_RTF"优先级 ="0x0000"type ="上下文">  
  
 \<父 guid ="guidCustomEditorCmdSet"id ="0"/ >  
  
 \<字符串 >  
  
 \<ButtonText > CustomEditor 上下文菜单\</ButtonText >  
  
 \<CommandName > CustomEditorContextMenu\</CommandName >  
  
 \</ 字符串 >  
  
 \</ 菜单 >  
  
 \</ 菜单 >  
  
 上面的文本将添加具有文本的上下文菜单命令**CustomEditor 上下文菜单**。 菜单 GUID 是使用此编辑器创建的命令集的一部分。 类型为"上下文"。  
  
 您还可以使用无需在中定义的预定义的命令 *.vsct*文件。 例如，检查*EditorPane.cs*由 Visual Studio 包模板生成的文件。 将为您的一组预定义命令，如<xref:Microsoft.VisualStudio.VSConstants.VSStd97CmdID>定义的<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>，如处理在命令处理程序中`onSelectAll`方法。  
  
## <a name="see-also"></a>请参阅  
 [命令、 菜单和工具栏](../extensibility/internals/commands-menus-and-toolbars.md)