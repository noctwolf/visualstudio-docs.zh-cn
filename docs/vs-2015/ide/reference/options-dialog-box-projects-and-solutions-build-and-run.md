---
title: “选项”对话框、项目和解决方案、生成和运行 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Projects.Build_and_Run
- VS.ToolsOptionsPag.Projects.Build_and_Run
helpviewer_keywords:
- builds [Visual Studio], setting up
- run actions
- debugger, run options
ms.assetid: c884976e-c0df-4c6d-8e3a-856ea2bd547c
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 38374893aea62af1b664065edf0ca9195f3dd301
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484321"
---
# <a name="options-dialog-box--projects-and-solutions-build-and-run"></a>选项对话框，项目和解决方案，生成和运行
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[选项对话框、 项目和解决方案、 生成和运行](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)。  
  
  
在此对话框中，可以指定可同时生成的 Visual C++ 或 Visual C# 项目的最大数量、某些默认生成行为及一些生成日志设置。 若要打开**选项**对话框框中，选择**工具**，**选项**菜单栏上。 若要访问此组选项，请展开**项目和解决方案**，然后选择**生成并运行**。  
  
## <a name="uielement-list"></a>UIElement 列表  
 **最大并行项目生成数**  
 指定可以同时生成的 Visual C++ 和 Visual C# 项目的最大数量。 若要优化生成过程，最大并行项目生成数自动设置为你的计算机的 CPU 数量。 最大数量为 32。  
  
 **在运行时仅生成启动项目和依赖项**  
 仅生成启动项目及其依赖项是如果时选择 F5 键; 选中此复选框选择**调试**，**启动**在菜单栏; 或选择**生成**，**生成**菜单栏上。 如果选择 F5 键; 时清除此复选框，则，生成所有项目、 依赖项和解决方案文件选择**调试**，**启动**在菜单栏; 或选择**生成**，**生成**菜单栏上。 默认情况下清除此选项。  
  
 **运行期间，当项目过期时**  
 > [!NOTE]
>  此列表仅适用于 [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] 项目。  
  
 默认情况下，出现一条消息如果项目配置已选择 F5 键或选择的日期**调试**，**启动**菜单栏上。 你可以指定是否仍要生成项目以及是否显示消息。 此选项用于指定是否将显示消息以及不显示消息时的生成行为。  
  
 **始终生成**  
 未出现此消息框，并且尽管有过期配置，仍生成项目。 此选项设置当你选择**不再显示此对话框**在消息框，然后选择**是**按钮。  
  
 **永远不会生成**  
 未出现此消息框，且未生成项目。 此选项设置当你选择**不再显示此对话框**在消息框，然后选择**否**按钮。  
  
 **提示生成**  
 每当项目配置过期时显示此消息框。  
  
 **运行期间，当出现生成或部署错误时**  
 如果从生成启动时出现生成错误**生成**菜单中，将显示一条消息。 您可以指定是否要继续通过启动该应用程序和该消息将显示每次生成错误发生。 此选项用于指定是否将显示消息以及不显示消息时的行为。  
  
> [!NOTE]
>  此选项仅适用于 [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] 项目。  
  
 **提示启动**  
 在每次出现生成错误时显示一个消息框。  
  
 **不启动**  
 未出现此消息框，且未启动应用程序。 此选项设置当你选择**不再显示此对话框**消息框中的复选框，然后选择**否**按钮。  
  
 **启动早期版本**  
 未出现此消息框，且未启动应用程序的新生成版本。 此选项设置当你选择**不再显示此对话框**消息框中的复选框，然后选择**是**按钮。  
  
 **对于新解决方案，使用当前选定的项目作为启动项目**  
 如果选中该复选框，则新解决方案将当前选择的项目用作启动项目。  
  
 **MSBuild 项目生成输出详细信息**  
 确定出现在生成的“输出”窗口中的信息数。  
  
 **MSBuild 项目生成日志文件详细信息**  
 > [!NOTE]
>  此选项仅适用于 Visual C++ 项目。  
  
 确定写入到生成日志文件中的信息数，该文件位于 \\...\\ProjectName\Debug\\ProjectName.log。  
  
## <a name="see-also"></a>请参阅  
 [编译和生成](../../ide/compiling-and-building-in-visual-studio.md)



