---
title: URL 选取器对话框 （Visual Studio 中的 SharePoint 开发） |Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.VWD.URLPicker
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, URL picker
- SharePoint development in Visual Studio, designer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 517058c99a6ec5a297b95324decbb2cfcbe04271
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49950753"
---
# <a name="url-picker-dialog-box-sharepoint-development-in-visual-studio"></a>URL 选取器对话框 （Visual Studio 中的 SharePoint 开发）
  在“URL 选取器”对话框中，您可以选择文件，如位于项目中或运行 SharePoint 的本地服务器上的母版页文件或图像文件。  
  
 在能够选择某个文件以设置属性时，将会显示该对话框。 可以通过选择省略号按钮打开此对话框中 (![ASP.NET 移动设计器椭圆](../sharepoint/media/mwellipsis.gif "ASP.NET 移动设计器椭圆")) 中的各种属性旁边**属性**窗口。 省略号按钮时也会显示为 IntelliSense 提示您为中的某些属性赋值**源**在设计器视图。  
  
## <a name="uielement-list"></a>UIElement 列表
 **项目文件夹**  
 显示在项目中或运行 SharePoint 的本地服务器上定义的文件夹的列表。 选择展开按钮可显示子文件夹。  
  
 展开**项目**节点，以在项目中选择文件。 若要在对话框中显示为可选项，你的项目中的文件必须满足以下条件：  
  
- 该文件必须包含在映射的文件夹。  
  
- 该文件必须添加到解决方案包。  
  
- 文件不能位于另一个项目。  
  
  如果你想要引用未满足这些条件的文件，您必须手动输入文件的路径。  
  
  展开**Server**节点，以选择位于运行 SharePoint 的本地服务器的文件。 若要在对话框中显示为可选项，这些文件必须满足以下条件：  
  
- 该文件必须位于以下映射文件夹之一：**映像**，**布局**，或**controltemplates 设置样式**。  
  
- 文件不能位于 SharePoint 内容数据库。  
  
  如果你想要引用未满足这些条件的文件，您必须手动输入文件的路径。  
  
  **文件夹的内容**  
  显示选定文件夹中的文件的列表。 选择一个文件，然后选择**确定**按钮以关闭对话框，并将所选内容发送到调用它的进程。  
  
  **文件类型**  
  允许你从适合于正在执行的任务的一组文件中进行选择。  
  
## <a name="see-also"></a>请参阅
 [为 SharePoint 创建应用程序页](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [为 SharePoint 创建 web 部件](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [创建 web 部件或应用程序页的可重用的控件](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)   
  
