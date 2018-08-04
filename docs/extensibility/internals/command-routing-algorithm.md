---
title: 命令传送算法 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, routing
- command routing
ms.assetid: 998b616b-bd08-45cb-845f-808efb8c33bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c11b7d08821be981254162f930251968773a7c54
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2018
ms.locfileid: "39511582"
---
# <a name="command-routing-algorithm"></a>命令传送算法
在 Visual Studio 中由多个不同组件处理命令。 命令是从最内部的上下文中，基于当前所选内容路由到最外层的上下文 （也称为全局）。 有关详细信息，请参阅[命令可用性](../../extensibility/internals/command-availability.md)。  
  
## <a name="order-of-command-resolution"></a>命令解析顺序  
 通过以下级别的命令上下文传递的命令：  
  
1.  外接程序： 环境首先提供了到任何加载项存在的命令。  
  
2.  优先级命令： 使用注册这些命令<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterPriorityCommandTarget>。 它们为 Visual Studio 中的每个命令调用，并在其中注册的顺序调用。  
  
3.  上下文菜单命令： 位于上下文菜单上的命令首先提供给命令目标是提供到上下文菜单，并会为典型的路由。  
  
4.  工具栏设置命令目标： 在调用时注册这些命令目标<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell4.SetupToolbar2%2A>。 `pCmdTarget`参数可以是`null`。 如果不是`null`，则此命令目标用于更新您设置了工具栏上的任何命令。 如果 shell 设置您的工具栏，则它将传递为窗口框架`pCmdTarget`，以便该窗口框架，通过在工具栏流上的命令的所有更新都甚至当它不是处于焦点模式。  
  
5.  工具窗口： 工具窗口，通常可实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>接口，还应实现<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>接口，因此，当工具窗口是活动窗口时，Visual Studio 可以获取命令目标。 但是，如果工具窗口具有焦点位于**项目**窗口中，则该命令将路由到<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>是常见的选定项的父级的接口。 如果选择此选项跨多个项目，该命令将路由到<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution>层次结构。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>接口包含<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A>并<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>类似于上的相应命令的方法<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>接口。  
  
6.  文档窗口： 如果该命令有`RouteToDocs`中设置标志及其 *.vsct*文件，Visual Studio 会查找在文档视图对象，它是命令目标的实例<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>接口或的实例文档对象 (通常<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>接口或<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>接口)。 如果文档视图对象不支持该命令，Visual Studio 会将路由到命令<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>返回的接口。 （这是文档数据对象的可选接口）。  
  
7.  当前层次结构： 当前层次结构可以是拥有活动文档窗口或层次结构中所选的项目**解决方案资源管理器**。 Visual Studio 查找<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>当前，或处于活动状态，层次结构实现的接口。 在层次结构应支持在层次结构处于活动状态，即使项目项的文档窗口具有焦点时有效的命令。 但是，命令的应用时，才**解决方案资源管理器**具有必须使用支持焦点<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>接口并将其<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A>和<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>方法。  
  
     **剪切**，**副本**，**粘贴**，**删除**，**重命名**，**输入**，和**DoubleClick**命令需要特殊处理。 有关如何处理**删除**并**删除**命令在层次结构中，请参阅<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDeleteHandler>接口。  
  
8.  全局： 如果尚未由前面所述的上下文处理命令，Visual Studio 将尝试将其路由到拥有实现的命令的 VSPackage<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>接口。 如果 VSPackage 未已加载，它不会加载时 Visual Studio 会调用<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>方法。 仅当加载 VSPackage<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>调用方法。  
  
## <a name="see-also"></a>请参阅  
 [命令设计](../../extensibility/internals/command-design.md)