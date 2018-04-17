---
title: 差异沙盒解决方案与场解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, sandboxed solutions
- sandboxed solutions [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, farm solutions
- farm solutions [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2340e7001d159b34bba62e9ba4ef90c34845b156
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="differences-between-sandboxed-and-farm-solutions"></a>沙盒解决方案与场解决方案之间的差异
  编译 SharePoint 解决方案时，它将部署到 SharePoint 服务器并调试器将附加来调试它。 用于调试解决方案的过程依赖于沙盒解决方案属性的设置： 沙盒解决方案和场解决方案。  
  
 有关详细信息，请参阅[沙盒解决方案注意事项](../sharepoint/sandboxed-solution-considerations.md)。  
  
## <a name="farm-solutions"></a>场解决方案  
 场解决方案，承载于 IIS 工作进程 (W3WP.exe) 中，运行的代码，可能会影响整个场。 调试其沙盒解决方案属性设置为"场解决方案"SharePoint 项目时，系统的 IIS 应用程序池将回收之前 SharePoint 收回或部署功能，以便释放锁定由 IIS 工作进程的任何文件。 仅为 SharePoint 项目的站点 URL 提供服务的 IIS 应用程序池被回收。  
  
## <a name="sandboxed-solutions"></a>沙盒解决方案  
 沙盒解决方案，托管在 SharePoint 用户代码解决方案工作进程 (SPUCWorkerProcess.exe) 中，运行的代码，只会影响解决方案的网站集。 沙盒解决方案不在 IIS 工作进程中运行，因为 IIS 应用程序池和 IIS 服务器都必须重新启动。 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 将调试器附加到 SharePoint 中的 SPUserCodeV4 服务将自动触发的 SPUCWorkerProcess 过程和控件。 没有必要 SPUCWorkerProcess 进程回收加载解决方案的最新版本。  
  
## <a name="either-type-of-solution"></a>任一类型的解决方案  
 无论使用哪一类解决方案，[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]还会将调试器附加到浏览器启用客户端脚本调试。 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 使用脚本调试为此目的的引擎。 若要启用脚本调试，必须在得到提示时更改默认浏览器设置。  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 将调试器附加到运行当前站点的 W3WP 或 SPUCWorkerProcess 进程仅。 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 此外会将附加的托管 COM Plus 和工作流的调试引擎。  
  
## <a name="see-also"></a>请参阅  
 [调试 SharePoint 解决方案](../sharepoint/debugging-sharepoint-solutions.md)   
 [生成和调试 SharePoint 解决方案](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [沙盒解决方案注意事项](../sharepoint/sandboxed-solution-considerations.md)  
  
  