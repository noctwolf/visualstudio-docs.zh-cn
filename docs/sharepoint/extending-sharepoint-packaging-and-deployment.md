---
title: "扩展 SharePoint 打包和部署 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 2fa807472a0787f0f1ae4c61f074fd8bb3ad5055
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="extending-sharepoint-packaging-and-deployment"></a>扩展 SharePoint 打包和部署
  可以扩展 SharePoint 项目的打包和部署过程。
  
##  <a name="creating-deployment-steps"></a>创建部署步骤  
 部署 SharePoint 项目时，[!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)] 会执行一系列部署步骤。 Visual Studio 包含用于很多任务的内置部署步骤，如收回和添加解决方案。 但是，还可以创建自己的部署步骤。  
  
 有关演示如何创建部署步骤的演练，请参阅[演练： 为 SharePoint 项目创建自定义部署步骤](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)。  
  
##  <a name="creating-deployment-configurations"></a>创建部署配置  
 部署配置是一组针对给定项目执行，但可能会影响所有 SharePoint 项目项的部署步骤。 每个部署配置都包含一组在部署项目时执行的步骤，以及在收回项目时执行的另一组步骤。 [!INCLUDE[vs_current_short](../sharepoint/includes/vs-current-short-md.md)]包括两个内置部署配置，但你也可以创建你自己。 创建部署配置时，可以包含内置部署步骤和你创建的部署步骤。  
  
 有关演示如何创建部署配置的演练，请参阅[演练： 为 SharePoint 项目创建自定义部署步骤](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)。  
  
##  <a name="run-code-when-a-sharepoint-solution-is-deployed-or-retracted"></a>在部署或收回 SharePoint 解决方案时运行代码  
 可以处理事件以在部署或收回 SharePoint 解决方案时执行其他任务。 Visual Studio 会在以下情况下引发你可以处理的事件：  
  
-   为 SharePoint 项目项执行每个部署步骤之前和之后。 有关详细信息，请参阅[如何： 在执行运行代码时部署步骤](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)。  
  
-   在部署或收回 SharePoint 项目之前和之后 有关详细信息，请参阅[如何： 运行代码 SharePoint 项目时是部署或收回](../sharepoint/how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted.md)。  
  
##  <a name="handling-deployment-conflicts"></a>处理部署冲突  
 某些类型的 SharePoint 项目项（包括模块、Web 部件、列表实例和内容类型）提供了内置部署冲突解决方法。 部署包含这些项目项之一的解决方案时，Visual Studio 会首先检查 SharePoint 站点上是否已存在与所部署项中的文件具有相同名称、URL 或 ID 的文件。 如果存在冲突，则 Visual Studio 可以自动解决冲突，或者它可以提示你以确定你是要让 Visual Studio 解决冲突还是取消部署。 有关详细信息，请参阅[SharePoint 打包和部署疑难解答](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md)。  
  
 可以通过提供自己的检查和解决部署冲突的代码，来扩展此功能。 有关详细信息，请参阅[如何： 处理部署冲突](../sharepoint/how-to-handle-deployment-conflicts.md)。  
  
##  <a name="run-command-line-operations-before-or-after-a-project-is-deployed"></a>部署项目之前或之后运行命令行操作  
 如果要在部署 SharePoint 解决方案时运行命令行操作，则可以设置 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> 对象的 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.PreDeploymentCommand%2A> 和 <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.PostDeploymentCommand%2A> 属性。 Visual Studio 会在部署项目之前和之后执行这些命令。  
  
 在某些情况下，可能会发生部署冲突。 可通过多种不同的方式来解决冲突。 有关详细信息，请参阅[SharePoint 打包和部署疑难解答](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md)。  
  
##  <a name="customizing-validation-rules"></a>自定义验证规则  
 部署解决方案包 (.wsp) 之前，可以创建自定义功能和包验证规则来验证功能或包是否有效。 例如，可以向开发人员报告信息、警告或错误以帮助他们解决验证问题。 有关详细信息，请参阅[如何： 创建自定义功能和包验证规则，为 SharePoint 解决方案](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何： 在执行运行代码时部署步骤](../sharepoint/how-to-run-code-when-deployment-steps-are-executed.md)   
 [演练： 为 SharePoint 项目创建自定义部署步骤](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)   
 [如何： 为 SharePoint 解决方案创建自定义功能和包验证规则](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md)   
 [扩展 SharePoint 项目系统](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  
