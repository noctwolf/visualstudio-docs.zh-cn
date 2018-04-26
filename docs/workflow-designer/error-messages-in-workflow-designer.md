---
title: 工作流设计器中的错误消息
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- WFDErrorMessages.UI
- System.Activities.Presentation.ErrorActivity.UI
- System.Activities.Presentation.View.ErrorView.UI
ms.assetid: 4d8bbc2e-34fc-477f-9140-4adfd70c34a0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c644922f240cd07c47e68e65432289c68bbe318
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="error-messages-in-workflow-designer"></a>工作流设计器中的错误消息

本主题介绍可以使用 Windows 工作流设计器时遇到的错误消息的类型。

## <a name="situations-in-which-errors-in-the-workflow-designer-occur"></a>工作流设计器中出现错误的情况

在以下情况下会发生在工作流设计器中的错误：

1.  表达式中存在错误。

2.  活动的验证约束未满足。

3.  XAML 文件中存在错误，导致活动无法加载。

4.  XAML 文件中存在错误，导致工作流无法加载。

无效的表达式和未满足的验证约束不会导致工作流无法生成。 会成功生成工作流，但在运行时将引发 <xref:System.Activities.InvalidWorkflowException>。 如果 XAML 文件中存在错误，生成将失败。

在 Visual Studio 时加载工作流时，其错误都显示在**错误列表**。 若要导航到错误的源的活动，双击中的错误**错误列表**。

### <a name="expression-errors"></a>表达式错误
 无效表达式用红色圆圈表示，并且该表达式旁有一个白色感叹号。 悬停在此图标上将显示描述错误来源的工具提示。 在 Visual Studio 中，单击要查看错误来源加下划线的行的表达式。 悬停在此加下划线的文本上将显示描述错误来源的工具提示。

### <a name="activity-validation-errors"></a>活动验证错误
 活动的验证约束未满足时，红色圆圈及白色感叹号显示在该活动的右上角。 悬停在此图标上将显示描述错误来源的工具提示。

### <a name="xaml-load-errors"></a>XAML 加载错误
 当活动失败时加载时，将显示一个红框以文本"活动无法加载由于 XAML 中的错误"。 这通常发生在无法解析活动的类型。 可以在设计器中删除无效的活动，方法是选中红色框，然后删除它。

### <a name="workflow-load-errors"></a>工作流加载错误
 当工作流失败时加载时，文本"工作流设计器遇到问题与您的文档"将显示在设计器图面，以及导致工作流加载失败的异常信息。 这通常发生在无法分析 XAML 文件时。