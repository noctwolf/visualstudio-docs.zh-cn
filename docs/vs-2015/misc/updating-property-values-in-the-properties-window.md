---
title: 属性窗口中更新属性值 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Properties window, updating property values
- property values, updating in Properties window
ms.assetid: 9358e8c3-b9d2-4fd4-aaab-cf48d1526db4
caps.latest.revision: 9
manager: douge
ms.openlocfilehash: 0272ba348e29fb1a2a118a0ff4b0989a2aa1683f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477168"
---
# <a name="updating-property-values-in-the-properties-window"></a>在“属性”窗口中更新属性值
有两种方法可以保持“属性”  窗口与属性值更改同步。 第一种是调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>接口，它提供了基本窗口化功能，包括访问和创建由环境提供的工具和文档窗口访问。 下面的步骤介绍了此同步过程。  
  
## <a name="updating-property-values-using-ivsuishell"></a>使用 IVsUIShell 更新属性值  
  
#### <a name="to-update-property-values-using-the-ivsuishell-interface"></a>使用 IVsUIShell 接口更新属性值  
  
1.  调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>(通过<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>服务) 时，只要 Vspackage、 项目或编辑器需要创建或枚举工具或文档窗口。  
  
2.  实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.RefreshPropertyBrowser%2A>保持**属性**窗口与属性更改为项目同步 (或浏览的任何其他所选对象**属性**窗口) 而无需实现<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>并触发<xref:Microsoft.VisualStudio.OLE.Interop.IPropertyNotifySink.OnChanged%2A>事件。  
  
3.  实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>方法<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.AdviseHierarchyEvents%2A>并<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.UnadviseHierarchyEvents%2A>建立并禁用，请分别，而无需在层次结构的层次结构事件的客户端通知，以实现<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>。  
  
## <a name="updating-property-values-using-iconnection"></a>使用 IConnection 更新属性值  
 第二种保持“属性”  窗口与属性值更改同步的方法是，实现可连接对象上的 `IConnection` ，以指示输出接口是否存在。 如果你想要本地化的属性名称，派生从对象<xref:System.ComponentModel.ICustomTypeDescriptor>。 <xref:System.ComponentModel.ICustomTypeDescriptor>实现可以修改它将返回的属性说明符和更改的属性名称。 若要本地化说明，创建派生的属性<xref:System.ComponentModel.DescriptionAttribute>并重写 Description 属性。  
  
#### <a name="considerations-in-implementing-the-iconnection-interface"></a>实现 IConnection 接口的注意事项  
  
1.  `IConnection` 提供对使用的枚举器子对象的访问<xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints>接口。 它还提供访问所有连接点子对象，它可以实现的每个<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint>接口。  
  
2.  任何浏览对象负责实施<xref:Microsoft.VisualStudio.OLE.Interop.IPropertyNotifySink>事件。  “属性”窗口通过 `IConnection`为事件集提供建议。  
  
3.  连接点用于控制连接数 （一个或多个） 它允许在其实现<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A>。 只允许一个接口的连接点可以返回<xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL>从<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.EnumConnections%2A>方法。  
  
4.  客户端可以调用`IConnection`要获得访问权限的枚举器子对象的接口<xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints>接口。 <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints>接口然后可以调用以枚举连接点的每个输出接口 ID (IID)。  
  
5.  `IConnection` 也可以调用以获取连接点使用的子对象的访问<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint>每个输出 IID 的接口。 通过<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint>接口，客户端启动或终止与可连接对象和客户端同步的通知循环。客户端还可以调用<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint>接口，以获得具有的枚举器对象<xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnections>要枚举其识别连接的接口。  
  
## <a name="see-also"></a>请参阅  
 [宣布属性窗口选定内容跟踪](../misc/announcing-property-window-selection-tracking.md)   
 [扩展属性](../extensibility/internals/extending-properties.md)