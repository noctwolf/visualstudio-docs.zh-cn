---
title: 自定义控件绑定对话框的 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.datasource.datauicustomization
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- Customize Control Binding dialog box
ms.assetid: abcc0be3-a18e-4f47-b354-d6b0c618e087
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 4d47fe3962651db91dcfdf6e59653db539a9f44b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478258"
---
# <a name="customize-control-binding-dialog-box"></a>“自定义控件绑定”对话框
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

使用**自定义控件绑定**对话框可以指定哪些控件中的项可用[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)。  
  
 中的每项**数据源**窗口具有关联的控件可以绑定到项的列表。 可用于每个项的控件取决于项的数据类型。 每种数据类型已在此对话框，其中包括一个默认的控件中定义的有效关联控件的列表。  
  
 将项拖动到设计图面来创建数据绑定控件之前，您可以选择要创建的控件。 如果中的项拖**数据源**窗口拖到设计图面，而无需为所选的项的数据类型添加到设计图面上选择的控件的默认控件。  
  
 详细了解如何使用此对话框中自定义控件中的项列表**数据源**窗口中，请参阅[将自定义控件添加到数据源窗口](../data-tools/add-custom-controls-to-the-data-sources-window.md)。  
  
## <a name="uielement-list"></a>UIElement 列表  
 **数据类型**  
 显示将与控件关联的类型的列表：  
  
-   表、 实体和对象表示为 **[列表]** 类型。  
  
-   实体和对象的公共属性或列表示为基础数据存储区中的属性的列的实际数据类型。  
  
-   具有用户定义的对象表示为 **[其他]**。 例如，如果你的应用程序具有显示来自多个对象的属性的数据的自定义控件，则选择 **[其他]** 为您的控件的数据类型。  
  
 **关联的控件**  
 显示您可以将与特定的数据类型相关联的控件的列表。 如果你想要将特定控件中选定的数据类型与相关联**数据类型**列表中，选择相应的复选框。 清除复选框以删除关联。 检查显示的快捷菜单中显示控件**数据源**窗口关联的数据类型的项。  
  
 可以通过将有一个到多个数据绑定属性的控件添加到列表中添加控件**工具箱**。 有关详细信息，请参阅[将自定义控件添加到数据源窗口](../data-tools/add-custom-controls-to-the-data-sources-window.md)。  
  
 **设置默认值**  
 将分配将选定的控件类型的默认值为所选的数据类型的项。 默认控件将作为显示的快捷菜单中的第一个选择出现**数据源**窗口中的项。 只有一个控件类型可以为数据类型的默认分配。  
  
 **清除默认值**  
 删除所选的数据类型的默认设置为指定的控件。 如果没有为所选的数据类型，无默认值 **[无]** 显示为显示的快捷菜单中的第一个选择**数据源**窗口关联的类型的项。  
  
## <a name="see-also"></a>请参阅  
 [“数据源”窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)   
 [添加新数据源](../data-tools/add-new-data-sources.md)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [将自定义控件添加到数据源窗口](../data-tools/add-custom-controls-to-the-data-sources-window.md)   
 [设置从“数据源”窗口中拖动时要创建的控件](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)