---
title: VisibilityItem 元素 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VisibilityItem element (VSCT XML schema)
- VSCT XML schema elements, VisibilityItem
ms.assetid: 0932f551-972d-4194-84bb-426e3e4375e4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 85cc2a3d65d5a4763aeca231175201cf55a74b3e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31143460"
---
# <a name="visibilityitem-element"></a>VisibilityItem 元素
`VisibilityItem`元素确定的静态可见性命令和工具栏。 每个条目标识命令或菜单上，以及关联的命令 UI 上下文。 Visual Studio 检测命令、 菜单和工具栏和可见性，而无需加载定义它们的 Vspackage。 IDE 使用<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A>方法来确定命令 UI 上下文是否处于活动状态。  
  
 加载 VSPackage 后，Visual Studio 期望命令可见性，将由 VSPackage 而不是`VisibilityItem`。 若要确定命令的可见性，你可以实现<xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>事件处理程序或<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>方法，具体取决于你的命令的实现方式。  
  
 命令或具有的菜单`VisibilityItem`仅当相关联的上下文处于活动状态时显示的元素。 你可以关联与一个或多个命令 UI 上下文的单个命令、 菜单或工具栏，方法是包括每个命令上下文组合的条目。 如果与多个命令 UI 上下文关联的命令或菜单，然后命令或菜单时才可见的关联的命令 UI 任何的上下文一个处于活动状态。  
  
 `VisibilityItem`元素仅适用于命令、 菜单和工具栏，不适用于组。 没有相关的元素`VisibilityItem`元素是可见的只要其父菜单处于活动状态。  
  
## <a name="syntax"></a>语法  
  
```  
<VisibilityItem  
  guid ="="cmdGuidMyProductCommands"  
  id=="cmdidAddWidget"  
  context="guidNotViewSourceMode"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|guid|必须的。 GUID/ID 命令标识符的 GUID。|  
|id|必须的。 GUID/ID 命令标识符的 ID。|  
|Context — 上下文|必须的。 该命令处于可见 UI 上下文。|  
|条件|可选。 请参阅[条件属性](../extensibility/vsct-xml-schema-conditional-attributes.md)。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[VisibilityConstraints 元素](../extensibility/visibilityconstraints-element.md)|`VisibilityConstraints`元素确定的命令和工具栏的组的静态可见。|  
  
## <a name="remarks"></a>备注  
 在中定义的标准的 Visual Studio UI 上下文*Visual Studio SDK 安装路径*\VisualStudioIntegration\Common\Inc\vsshlids.h 文件以及作为 in<xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids>和<xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>类。 在中定义一组更为完整的 UI 上下文<xref:Microsoft.VisualStudio.VSConstants>类。  
  
## <a name="example"></a>示例  
  
```  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A>   
 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>   
 <xref:Microsoft.VisualStudio.VSConstants>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>   
 [VisibilityConstraints 元素](../extensibility/visibilityconstraints-element.md)   
 [Visual Studio 命令表格 (.Vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)