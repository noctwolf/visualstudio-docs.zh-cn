---
title: CommandTable 元素 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- CommandTable
helpviewer_keywords:
- CommandTable element (VSCT XML schema)
- VSCT XML schema elements, CommandTable
ms.assetid: 15c38159-660a-4ef4-9643-aa6fcfca82a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1d3869a9d3350daac8b08398ed5afaab0729a05c
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44278876"
---
# <a name="commandtable-element"></a>CommandTable 元素
CommandTable 是根元素 *.vsct*文件。 这是定义的实际布局和 VSPackage 提供对 IDE 的命令的类型的文件。 命令可能包括菜单项、 菜单、 工具栏和组合框。 有关详细信息，请参阅[Visual Studio 命令表格 (.vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)。  
  
## <a name="syntax"></a>语法  
  
```xml  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema" >  
  <Extern>... </Extern>  
  <Include>... </Include>  
  <Define>... </Define>  
  <Commands>... </Commands>  
  <CommandPlacements>... </CommandPlacements>  
  <VisibilityConstraints>... </VisibilityConstraints>  
  <KeyBindings>... </KeyBindings>  
  <UsedCommands... </UsedCommands>  
  <Symbols>... </Symbols>  
</CommandTable>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|xmlns|必须的。 XML 命名空间：<br /><br /> xmlns ="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable"<br /><br /> xmlns:xs ="http://www.w3.org/2001/XMLSchema"|  
|语言|可选。 语言特性可用于指定的默认语言的所有\<字符串 > 命令表中的元素。  如果未指定语言，将使用当前进程的语言：<br /><br /> 语言 ="en-我们"|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[Extern 元素](../extensibility/extern-element.md)|可选。 包含用于编译器预处理器指令。|  
|[包含元素](../extensibility/include-element.md)|可选。 包含要包括在编译中的任何文件的路径。|  
|[定义元素](../extensibility/define-element.md)|可选。 定义给定其名称和值的符号。|  
|[Commands 元素](../extensibility/commands-element.md)|可选。 父元素定义的所有命令的 VSPackage，其中包含所有其他元素。|  
|[CommandPlacements 元素](../extensibility/commandplacements-element.md)|可选。 定义命令栏上的命令的位置放置。|  
|[VisibilityConstraints 元素](../extensibility/visibilityconstraints-element.md)|可选。 确定命令和工具栏的静态可见性。|  
|[KeyBindings 元素](../extensibility/keybindings-element.md)|可选。 指定快捷键组合，如果有，这些命令。|  
|[UsedCommands 元素](../extensibility/usedcommands-element.md)|可选。 允许 VSPackage 来选择实现其自己的版本最初由其他 Vspackage 支持的功能。|  
|[Symbols 元素](https://www.microsoft.com/download/details.aspx?id=55984)|可选。 包含编译器任何符号数据-Guid 和 Id，等。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|无||  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令表格 (.vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)