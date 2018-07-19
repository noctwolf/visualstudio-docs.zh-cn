---
title: 如何： 设置 SharePoint 部署命令 |Microsoft Docs
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
ms.openlocfilehash: 060acd0164ff7819d2abfb8d92f2394b4bcc0672
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118808"
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>如何： 设置 SharePoint 部署命令
  通过设置预先部署脚本和后期部署命令，可以自定义部署过程。 当调试从 Visual Studio 的 SharePoint 解决方案时，这些命令运行之前和之后的其他部署操作。  
  
### <a name="to-add-a-pre-deployment-command"></a>若要添加预先部署命令  
  
1.  在菜单栏上依次选择**项目** > **\<*ProjectName*> 属性**。  
  
2.  选择**SharePoint**选项卡。  
  
3.  在中**预先部署命令行**文字框中，输入自定义此步骤的 MS-DOS 或 MSBuild 命令。  
  
     例如，若要在部署完成之前，请列出目录内容，请输入**dir**。  
  
### <a name="to-add-a-post-deployment-command"></a>若要添加后期部署命令  
  
1.  在菜单栏上依次选择**项目** > **\<*ProjectName*> 属性**。  
  
2.  选择**SharePoint**选项卡。  
  
3.  在中**后期部署命令行**文字框中，输入自定义此步骤的 MS-DOS 或 MSBuild 命令。  
  
     例如，若要完成部署后列出目录内容，请输入**dir**。 若要使用 MSBuild 变量从生成目录复制程序集，请输入**复制 $ （targetpath) c:\DeploymentDirectory**。  
  
## <a name="see-also"></a>请参阅
 [打包和部署 SharePoint 解决方案](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
