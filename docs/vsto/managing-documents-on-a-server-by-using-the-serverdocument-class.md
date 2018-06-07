---
title: 使用 ServerDocument 类管理服务器上的文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], managing on server
- Office documents [Office development in Visual Studio, managing on server
- ServerDocument class, managing documents on server
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 97eed0e4cec143e51195347bfb90d430d8e1eadb
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572993"
---
# <a name="manage-documents-on-a-server-by-using-the-serverdocument-class"></a>使用 ServerDocument 类管理服务器上的文档
  你可以使用`ServerDocument`类[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]管理几个方面的文档级自定义项，即使未安装 Microsoft Office Word 和 Microsoft Office Excel。 你可以执行以下任务：  
  
-   访问和修改文档或工作簿的数据缓存中的数据。 有关详细信息，请参阅[工作与在文档中缓存的数据](#CachedData)。  
  
-   管理与文档相关联的自定义项程序集。 有关详细信息，请参阅[管理文档自定义项](#CustomizationInfo)。  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="understand-the-serverdocument-class"></a>了解 ServerDocument 类  
 `ServerDocument`类旨在在没有安装 Office 的计算机上使用。 因此，你通常使用此类应用程序执行不会与集成 Office，如控制台项目或 Windows 窗体项目，而不是 Office 项目中。 使用<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>类*Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll*程序集。  
  
 `ServerDocument`类可以用于对通过使用创建的文档级自定义项进行操作[!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]。  
  
 有关详细信息 Visual Studio 2010 Tools for Office Runtime 和 Office 扩展的.NET framework，请参阅[Visual Studio Tools for Office runtime 概述](../vsto/visual-studio-tools-for-office-runtime-overview.md)。  
  
> [!NOTE]  
>  如果使用的旧应用程序`ServerDocument`类`Visual Studio Tools for Office`system (3.0 版运行时)，则`Visual Studio Tools for Office`system （3.0 版运行时） 必须安装在运行该应用程序的计算机上。 `Visual Studio 2010 Tools for Office runtime`无法运行这些应用程序。  
  
##  <a name="CachedData"></a> 使用文档中的缓存数据  
 `ServerDocument`类提供了可用于处理与数据缓存在自定义文档中的成员。 有关缓存数据的详细信息，请参阅[缓存数据](../vsto/caching-data.md)和[访问服务器上的文档中的数据](../vsto/accessing-data-in-documents-on-the-server.md)。  
  
 下表列出可用于处理与缓存的数据的成员。  
  
|任务|供使用的成员|  
|----------|-------------------|  
|若要确定文档是否有数据缓存。|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.IsCacheEnabled%2A> 方法。|  
|若要访问文档中缓存的数据。<br /><br /> 有关详细信息，请参阅[访问服务器上的文档中的数据](../vsto/accessing-data-in-documents-on-the-server.md)。|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 属性。|  
  
##  <a name="CustomizationInfo"></a> 管理文档自定义项  
 你可以使用的成员`ServerDocument`类来管理与文档相关联的自定义项程序集。 例如，你可以以编程方式删除自定义项从文档使该文档不再是一部分的自定义项。  
  
 下表列出可用于管理自定义程序集的成员。  
  
|任务|供使用的成员|  
|----------|-------------------|  
|若要确定文档是否是在文档级自定义项的一部分。|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.GetCustomizationVersion%2A> 方法。|  
|若要以编程方式将自定义项附加在运行时向文档中。<br /><br /> 有关详细信息，请参阅[如何： 附加托管代码扩展到文档](../vsto/how-to-attach-managed-code-extensions-to-documents.md)|之一<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A>方法。|  
|若要在运行时以编程方式删除文档中的自定义项。<br /><br /> 有关详细信息，请参阅[如何： 删除文档从托管代码扩展](../vsto/how-to-remove-managed-code-extensions-from-documents.md)。|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> 方法。|  
|若要获取的部署清单的与文档相关联的 URL。|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.DeploymentManifestUrl%2A> 属性。|  
  
## <a name="see-also"></a>请参阅  
 [如何： 附加托管代码扩展到文档](../vsto/how-to-attach-managed-code-extensions-to-documents.md)   
 [如何： 删除文档从托管代码扩展](../vsto/how-to-remove-managed-code-extensions-from-documents.md)   
 [Visual Studio Tools for Office runtime 概述](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [缓存数据](../vsto/caching-data.md)  
  