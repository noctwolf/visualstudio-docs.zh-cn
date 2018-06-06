---
title: 扩展服务器资源管理器中的 SharePoint 连接节点 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint Connections [SharePoint development in Visual Studio], extending a node
- SharePoint development in Visual Studio, extending SharePoint Connections node in Server Explorer
- SharePoint Connections [SharePoint development in Visual Studio], creating a new node type
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 433923234b890564d21915d56a906fe10060e4ae
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766267"
---
# <a name="extend-the-sharepoint-connections-node-in-server-explorer"></a>扩展服务器资源管理器中的 SharePoint 连接节点
  在 Visual Studio 中，你可以连接到开发计算机上的本地 SharePoint 站点使用**SharePoint 连接**中的节点**服务器资源管理器**窗口。 此节点显示许多本地 SharePoint 站点组件在分层树视图中。 例如，你可以在本地站点上查看的列表、 文档库和内容类型。 有关使用**服务器资源管理器**若要连接到本地 SharePoint 站点，请参阅[浏览 SharePoint 连接使用服务器资源管理器](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)。  
  
 你可以扩展**SharePoint 连接**节点通过创建现有节点的扩展或创建自定义节点类型，并将其添加到节点的层次结构。  
  
## <a name="tasks-for-extending-the-sharepoint-connections-node"></a>用于扩展 SharePoint 连接节点的任务
 若要扩展的现有节点，创建一个 Visual Studio 扩展，实现<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension>接口。 扩展一个节点时，你可以将功能添加到如快捷菜单项或自定义属性的节点。 有关详细信息，请参阅[如何： 扩展服务器资源管理器中的 SharePoint 节点](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)。  
  
 若要创建自定义节点类型，创建一个 Visual Studio 扩展，实现<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider>接口。 如果你想要显示的 SharePoint 网站的不会显示在组件创建一个自定义节点**服务器资源管理器**默认情况下。 例如，**服务器资源管理器**不可以添加默认情况下，但你的 SharePoint 站点的 Web 部件库中不显示执行此自定义节点。 有关详细信息，请参阅[如何： 向服务器资源管理器中添加自定义 SharePoint 节点](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)和[演练： 扩展服务器资源管理器显示 Web 部件](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)。  
  
## <a name="add-custom-properties-to-nodes"></a>将自定义属性添加到节点
 当你扩展的节点，或创建自定义节点类型时，你可以将自定义属性添加到节点。 属性将显示在**属性**窗口时选择的节点。  
  
 有两种类型的可以向节点添加的自定义属性：  
  
-   显示从 SharePoint 站点的只读数据的一组的属性。 数据描述该节点表示 SharePoint 组件。 有关演示如何执行此操作的演练，请参阅[演练： 扩展服务器资源管理器显示 Web 部件](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)。  
  
-   显示自定义的读/写数据的属性。 有关演示如何执行此操作的代码示例，请参阅[如何： 扩展服务器资源管理器中的 SharePoint 节点](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)。  
  
## <a name="get-data-for-built-in-nodes"></a>为内置节点获取数据
 所有 Visual Studio 提供的内置节点包括有关 SharePoint 组件表示的一些数据。 例如，表示 SharePoint 站点上的列表的节点提供有关列表中，如标题和列表的默认视图的 URL 的一些数据。  
  
 若要访问此数据，检索中的数据对象<xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A>属性<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode>对象，表示你感兴趣的节点。 数据对象的类型取决于节点的类型。  
  
 下面的代码示例演示如何获取列表节点的数据对象。 若要查看此示例中的上下文中的一个更大的示例，请参阅[如何： 在服务器资源管理器中的内置 SharePoint 节点获取数据](../sharepoint/how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer.md)。  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#11](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/serverexplorerextensionnodeinfo.vb#11)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#11](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/serverexplorerextensionnodeinfo.cs#11)]  
  
 下表列出每个内置的节点类型的数据对象类型。  
  
|节点类型|数据对象类型|  
|---------------|----------------------|  
|SharePoint 网站节点|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerSiteNodeInfo>|  
|内容类型|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IContentTypeNodeInfo>|  
|功能|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IFeatureNodeInfo>|  
|字段|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IFieldNodeInfo>|  
|列表|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListNodeInfo>|  
|列表模板|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListTemplateNodeInfo>|  
|列表视图 (Microsoft.SharePoint.SPView)|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IListViewNodeInfo>|  
|工作流关联|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IWorkflowAssociationNodeInfo>|  
|工作流模板|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions.IWorkflowTemplateNodeInfo>|  
  
 有关使用<xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A>属性，请参阅[关联与 SharePoint 工具扩展的自定义数据](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)。  
  
## <a name="see-also"></a>请参阅
 [演练： 扩展服务器资源管理器以显示 Web 部件](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [如何： 扩展服务器资源管理器中的 SharePoint 节点](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md)   
 [如何： 向服务器资源管理器中添加自定义 SharePoint 节点](../sharepoint/how-to-add-a-custom-sharepoint-node-to-server-explorer.md)   
 [如何： 在服务器资源管理器中的内置 SharePoint 节点获取数据](../sharepoint/how-to-get-data-for-a-built-in-sharepoint-node-in-server-explorer.md)   
 [将自定义数据与 SharePoint 工具扩展相关联](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)   
 [使用服务器资源管理器浏览 SharePoint 连接](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [在 Visual Studio 中扩展 SharePoint 工具](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)  
  
  
