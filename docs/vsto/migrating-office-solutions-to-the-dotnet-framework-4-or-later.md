---
title: 将 Office 解决方案迁移到.NET Framework 4 或更高版本 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.Project.TargetFrameworkWarning
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7ac244bebb1a625c7858a62399ee79126e309cf2
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2018
ms.locfileid: "34571794"
---
# <a name="migrating-office-solutions-to-the-net-framework-4-or-later"></a>将 Office 解决方案迁移到.NET Framework 4 或更高版本
  如果将 Office 项目的目标框架从 .NET Framework 的早期版本更改为 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 或更高版本，则可能需要执行一些其他步骤才能继续运行开发计算机和最终用户计算机上的解决方案。 有关详细信息，请参阅[所需更改即可运行你迁移到.NET Framework 4 或.NET Framework 4.5 的 Office 项目](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)。  
  
 此外，可能无法再编译该项目。 对于不同版本的 .NET Framework，Office 项目的一些功能具有不同的编程模型。 当 Office 项目的目标框架从 .NET Framework 的早期版本更改为 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 或更高版本时，必须对项目进行以下代码更改：  
  
-   [更新迁移到.NET Framework 4 或.NET Framework 4.5 的 Excel 和 Word 项目](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [更新迁移到.NET Framework 4 或.NET Framework 4.5 的 Office 项目中的功能区自定义](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [更新迁移到.NET Framework 4 或.NET Framework 4.5 的 Outlook 项目中的窗体区域](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
 当从 Visual Studio 的早期版本升级该项目时，Office 项目的目标框架将更改。 有关详细信息，请参阅[升级和迁移 Office 解决方案](../vsto/upgrading-and-migrating-office-solutions.md)。  
  
 有关原因的详细信息中的 Office 项目的某些功能具有不同的编程模型，当你面向[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]或更高版本，请参阅[更改为面向.NET Framework 4 或.NET Framework 4.5Office项目的设计](../vsto/changes-to-the-design-of-office-projects-that-target-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)和[Visual Studio Tools for Office runtime 概述](../vsto/visual-studio-tools-for-office-runtime-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 [设计和创建 Office 解决方案](../vsto/designing-and-creating-office-solutions.md)   
 [如何： 面向.NET Framework 版本](../ide/how-to-target-a-version-of-the-dotnet-framework.md)   
 [解决 Office 解决方案中的错误](../vsto/troubleshooting-errors-in-office-solutions.md)   
 [在 Office 解决方案中的错误的附加支持](../vsto/additional-support-for-errors-in-office-solutions.md)  
  
  