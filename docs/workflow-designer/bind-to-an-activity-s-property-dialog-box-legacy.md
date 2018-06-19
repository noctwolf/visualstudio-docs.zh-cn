---
title: 工作流设计器-将绑定到活动&#39;s 属性对话框 （旧版）
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Workflow.ComponentModel.Design.ActivityBindForm.UI
helpviewer_keywords:
- Bind to an Activity's Property dialog box
ms.assetid: 19ebb207-e0a9-4642-8f5f-a5e31395c683
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8922864a32c08d8feaed11e530314176557a785f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31970980"
---
# <a name="bind-to-an-activitys-property-dialog-box-legacy"></a>“绑定到活动的属性”对话框（旧版）

本主题介绍如何使用**将绑定到活动的属性**旧的 Windows 工作流设计器中的对话框。 当你需要以面向.NET Framework 版本 3.5 或 WinFX 时，请使用旧工作流设计器。

 依赖项属性的实例类型可以绑定到另一个活动的公共属性或事件。 有关活动绑定的详细信息，请参阅[使用依赖项属性](http://go.microsoft.com/fwlink?LinkID=65007)。

 选择要绑定到使用的属性**将绑定到活动的属性**对话框。 通过单击省略号打开此对话框 **[…]** 中所选的属性的文本框末尾**属性**窗口中，或通过单击出现在属性浏览器中的属性名称旁边的蓝色感叹号图标。

 下表描述的用户界面 (UI) 元素**将绑定到活动的属性**对话框。

|UI 元素|描述|
|----------------|-----------------|
|**将绑定到的现有成员**|在树视图窗格中，选择要绑定到的成员。 树视图下面的窗格显示了一条消息，此消息指示成员是否为有效的要绑定到的类型。 单击**确定**要绑定到选定的有效成员。|
|**将绑定到新的成员**|创建要绑定到的新成员字段或属性。 输入**新成员名称**。 选择是否想要通过选择创建依赖项属性或公共字段**创建字段**或**创建属性**。 单击**确定**若要创建新的成员。|

## <a name="see-also"></a>请参阅

- [使用活动属性](http://go.microsoft.com/fwlink?LinkID=65013)
- [使用依赖项属性](http://go.microsoft.com/fwlink?LinkID=65007)
- [Windows Workflow Foundation 的旧版设计器 UI 帮助](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)