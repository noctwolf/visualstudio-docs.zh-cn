---
title: 如何： 设置 SharePoint 部署命令 |Microsoft 文档
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
- SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8779ba4ee4cf9803982d9849b3af7c83930d8a5b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>如何：设置 SharePoint 部署命令
  通过设置预先部署脚本和后期部署命令，你可以自定义部署过程。 调试从 Visual Studio 的 SharePoint 解决方案时，这些命令运行之前和之后的其他部署操作。  
  
### <a name="to-add-a-pre-deployment-command"></a>若要添加预先部署命令  
  
1.  在菜单栏上，选择**项目**，* ProjectName ***属性**。  
  
2.  选择**SharePoint**选项卡。  
  
3.  在**预先部署命令行**文本框中，输入 MS-DOS 或 MSBuild 命令，以自定义此步骤。  
  
     例如，若要在部署完成之前，请列出目录内容，请输入**dir**。  
  
### <a name="to-add-a-post-deployment-command"></a>若要添加后期部署命令  
  
1.  在菜单栏上，选择**项目**，* ProjectName ***属性**。  
  
2.  选择**SharePoint**选项卡。  
  
3.  在**后期部署命令行**文本框中，输入 MS-DOS 或 MSBuild 命令，以自定义此步骤。  
  
     例如，若要列出目录内容部署完成后，输入**dir**。 若要使用 MSBuild 变量的程序集复制从生成目录，输入**复制 $ （targetpath) c:\DeploymentDirectory**。  
  
## <a name="see-also"></a>请参阅  
 [打包和部署 SharePoint 解决方案](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  