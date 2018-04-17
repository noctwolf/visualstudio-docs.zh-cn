---
title: 如何： 将控件添加到 Backstage 视图 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- customizing the Ribbon, menus
- controls, Ribbon
- menus, customizing
- Microsoft Office Button
- custom Ribbon, menus
- Ribbon, customizing
- Office button
- Ribbon, menus
- Microsoft Office Menu
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1cdda3960363ba87e9434cd14077c7182a9f56c4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-controls-to-the-backstage-view"></a>如何：向 Backstage 视图添加控件
  你可以使用功能区设计器将控件添加到当单击打开菜单**文件**选项运行该应用程序，你将添加到的控件时**文件**选项卡会显示一个名为组**外接程序**。  
  
 您不能使用 Visual Studio 中的功能区设计器之前, 或之后内置控件放置控件。 内置控件是一个已出现在 Backstage 视图的控件。 如果你想要放置控件之前或之后内置控件，你必须使用功能区 XML。 有关详细信息**功能区 (XML)**，请参阅[功能区 XML](../vsto/ribbon-xml.md)。 有关自定义 Backstage 视图的详细信息，请参阅[开发人员在 Office 2010 Backstage 视图简介](http://go.microsoft.com/fwlink/?LinkId=182189)和[自定义开发人员在 Office 2010 Backstage 视图](http://go.microsoft.com/fwlink/?LinkId=182188)。  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-controls-to-backstage-view"></a>将控件添加到 Backstage 视图  
  
1.  在设计视图中打开功能区项。  
  
     有关如何添加**功能区 （可视化设计器）**到你的项目项，请参阅[如何： 开始使用自定义功能区](../vsto/how-to-get-started-customizing-the-ribbon.md)。  
  
2.  在功能区设计器中，单击**文件**选项卡。  
  
     菜单设计器随即出现。 此设计图面不包含任何控件。  
  
3.  从**Office 功能区控件**选项卡**工具箱**的任何以下控件拖到菜单设计器：  
  
    -   Button  
  
    -   CheckBox  
  
    -   库  
  
    -   菜单  
  
    -   Separator  
  
    -   SplitButton  
  
    -   ToggleButton  
  
4.  拖动控件以将它们移动到新位置中，在菜单上。  
  
## <a name="see-also"></a>请参阅  
 [功能区概述](../vsto/ribbon-overview.md)   
 [功能区设计器](../vsto/ribbon-designer.md)   
 [功能区 XML](../vsto/ribbon-xml.md)   
 [如何： 开始自定义功能区](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [演练：使用功能区设计器创建自定义选项卡](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)  
  
  