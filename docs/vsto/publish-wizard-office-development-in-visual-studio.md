---
title: 发布向导 （Visual Studio 中的 Office 开发） |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.ProjectProperties.PublishWizard
- VST.PublishWizard.Publish.2007System
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], Publish Wizard
- deploying applications [Office development in Visual Studio], Publish Wizard
- Office applications [Office development in Visual Studio], Publish Wizard
- Publish Wizard, Office solutions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 67e3222c6f1deeca58b84aca4ba73d2826483b26
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="publish-wizard-office-development-in-visual-studio"></a>发布向导（Visual Studio 中的 Office 开发）
  使用**发布向导**若要将解决方案文件复制到指定位置中，创建清单的文件，并创建的安装程序。  
  
 若要访问此向导中，在**生成**菜单上，选择**发布** *SolutionName*。 你也可以访问**发布向导**从**解决方案资源管理器**。 打开项目节点的快捷菜单，然后选择**发布**。  
  
 下面各节介绍向导的一页。  
  
## <a name="where-do-you-want-to-publish-the-application"></a>要其中发布应用程序？  
 **指定要发布此应用程序的位置**  
 必须的。 发布位置为目录其中**发布向导**将从生成复制解决方案文件，例如，清单、 程序集、 临时证书和其他文件。 你必须对此目录具有写权限。  
  
 键入作为磁盘路径、 文件共享、 FTP 站点或网站 URL 的位置或单击**浏览**按钮以浏览到该位置。 路径可以是以下格式：  
  
-   标准 Windows 格式，如 C:\Deploy\MyApplication 或 \MyApplication 的相对或绝对路径。  
  
-   通用命名约定 (UNC) 路径，如\\\ServerName\MyApplication\\。  
  
-   Web URL 站点，如http://www.microsoft.com/MyApplication。  
  
 默认情况下，发布位置是*http://localhost/projectname/*如果必须安装 IIS，或者如果你这样做的 publish\ 目录未安装 IIS。  
  
> [!NOTE]  
>  如果目标计算机正在运行 Windows Vista，有更多注意事项。 你必须是 Windows Vista 计算机上的管理员才能使用本地发布选项。 此外，默认位置是始终*发布\\*目录中，而不考虑是否可以安装 IIS。  
  
## <a name="what-is-the-default-installation-path-on-end-user-computers"></a>最终用户计算机上的默认安装路径是什么？  
 安装路径是可选的。 如果你愿意，你可以稍后设置的安装路径。 有关详细信息，请参阅[如何： 更改 Office 解决方案的安装路径](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd)。  
  
 安装路径是最终用户将从其中安装自定义项的目录。 这也是解决方案将用于检查更新的路径。 **发布向导**不未将解决方案部署到此位置，除非该路径与你在中输入相同**指定要发布此应用程序的位置**在前一页上的框。  
  
 **从网站**  
 指定最终用户将遵循用于安装解决方案的 URL。  
  
 **从 UNC 路径或文件共享**  
 指定最终用户将遵循用于安装解决方案的 UNC 路径。  
  
 **从 CD-ROM 或 DVD-ROM**  
 此选项不需要安装路径。  
  
 CD 或 DVD，不将刻录 visual Studio。 你必须手动将输出复制到 CD 或 DVD。  
  
## <a name="see-also"></a>请参阅  
 [通过使用 ClickOnce 部署 Office 解决方案](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [发布页、 项目设计器&#40;Visual Studio 中的 Office 开发&#41;](../vsto/publish-page-project-designer-office-development-in-visual-studio.md)   
 [部署 Office 解决方案](../vsto/deploying-an-office-solution.md)  
  
  