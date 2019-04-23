---
title: 如何：Office 项目中创建事件处理程序
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Basic [Office development in Visual Studio], event handlers
- event handlers [Office development in Visual Studio]
- Visual C# [Office development in Visual Studio], event handlers
- events [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 577b12be220e2a695609db6c508d7aaf69c79f92
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60054516"
---
# <a name="how-to-create-event-handlers-in-office-projects"></a>如何：Office 项目中创建事件处理程序
  有几种方法在 Visual Basic 和 C# 中创建事件处理程序。 在设计视图中，可以通过双击控件，创建默认控件的事件处理程序或使用的事件窗格**属性**窗口控件上创建的任何事件处理程序。 但是，如果要在代码视图中，您可能不想要切换到设计视图若要创建事件处理程序。

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

### <a name="to-create-an-event-handler-in-visual-basic"></a>若要在 Visual Basic 中创建一个事件处理程序

1. 从**类名**在代码编辑器的顶部下拉列表中，选择想要为对象创建的事件处理程序。

    > [!NOTE]
    >  如果你想要创建的事件处理程序`ThisDocument`或`ThisWorkbook`，必须选择 **（ThisDocument 事件）** 或 **（ThisWorkbook 事件）** 中**类名**下拉列表

2. 从**方法名称**下拉列表顶部的代码编辑器中，选择该事件。

     Visual Studio 创建的事件处理程序，并将插入点移动到新创建的事件处理程序。 如果事件处理程序已存在，插入点移动到现有的事件处理程序。

### <a name="to-create-an-event-handler-in-c"></a>若要在 C 中创建一个事件处理程序\#

1. 创建中的事件委托**启动**通过键入一个空格后, 跟的限定的事件名称，然后键入类的事件**+=** 之后没有空格。 例如：

     `this.<object name>.<event name> +=`

2. 在代码行末尾，按 TAB 键两次。

     Visual Studio 会自动完成的代码行，创建事件处理程序，并将插入点移动到新创建的事件处理程序。

## <a name="see-also"></a>请参阅
- [在 Office 解决方案中编写代码](../vsto/writing-code-in-office-solutions.md)
- [演练：针对 NamedRange 控件的事件进行编程](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)
- [生成 Office 解决方案](../vsto/building-office-solutions.md)
