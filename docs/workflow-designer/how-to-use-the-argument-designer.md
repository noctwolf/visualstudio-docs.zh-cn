---
title: 工作流设计器-如何： 使用自变量设计器
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Presentation.View.ArgumentDesigner.UI
- System.Activities.Presentation.View.DesignTimeArgument.UI
ms.assetid: 64813fd5-1ea1-499a-98b4-ab2a44b7ee5e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b94656c7242c4bc6bc1dd1430230dac62a5322f1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-the-argument-designer"></a>如何：使用自变量设计器

与以前版本的.NET Framework 相比，自变量设计器可以轻松以允许数据流入和流出活动。 通过单击访问设计器**参数**设计画布左下角的按钮。 该设计器包含显示在表格窗体和可以按每一列标题排序除外的自变量列表**默认值**列。 每个自变量都包含名称、输入/输出/输入-输出/属性方向、类型和默认表达式值（如果有）。 名称和默认的表达式值都是可编辑的文本字段，类型和方向是下拉项。 有关详细信息，请参阅[变量和自变量 (.NET)](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)。

## <a name="to-create-a-new-argument"></a>创建新自变量

1.  在 Visual Studio 2010 中打开一个工作流或活动解决方案。

2.  通过单击打开参数设计器**参数**设计画布左下角的按钮。 此时将显示自变量设计器。

3.  单击标记为空的行**创建自变量**。 这会将新行添加使用新的自变量使用以下默认值： 为 argumentx**名称**其中 x 是一个整数，它自动递增，从而创建唯一的自变量名称的 1 的初始值**中**为**方向**，和**字符串**为**自变量类型**。 为添加任何值**默认值**。 可以在工作流设计过程中随时更改这些值。

    > [!NOTE]
    > 若要删除某个参数，通过单击选择的参数，然后按**删除**密钥。

## <a name="see-also"></a>请参阅

- [使用工作流设计器](../workflow-designer/using-the-workflow-designer.md)
- [变量和参数](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)