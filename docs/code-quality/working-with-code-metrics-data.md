---
title: Visual Studio 中的代码度量结果窗口
ms.date: 12/12/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b8400ce0d407af2318c4fffa19bc2b41e23f034d
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44284128"
---
# <a name="using-the-code-metrics-results-window"></a>使用代码度量结果窗口

**代码度量结果**窗口将显示生成的代码度量值分析的数据。 代码度量数据值的详细信息，请参阅[代码的指标值](../code-quality/code-metrics-values.md)。

## <a name="displaying-code-metrics-results"></a>显示代码度量结果

**代码度量结果**生成代码度量结果时，将自动显示窗口。 此外可以在任何时候显示窗口。

### <a name="to-display-the-code-metrics-results-window"></a>若要显示代码度量结果窗口

- 上**分析**菜单中，选择**Windows** > **代码度量结果**。

   \- 或 -

- 上**视图**菜单中，选择**其他 Windows** > **代码度量结果**。

**代码度量结果**显示窗口，即使不包含任何结果。

### <a name="to-view-code-metrics-details"></a>若要查看代码度量值详细信息

如果已生成代码度量结果，则展开的树中**层次结构**列。

## <a name="filtering-code-metrics-results"></a>筛选代码度量结果

您可以筛选结果中显示**代码度量结果**窗口是通过使用顶部的工具栏。 例如，您可能想要查看具有低于 65 可维护性索引的结果。

**筛选器**下拉列表框中包含的结果列的名称。 定义筛选器时，则将它添加到并进行缩进列表的底部。 该列表可以包含未定义的 10 个最新筛选器。

### <a name="to-filter-the-code-metrics-results"></a>若要筛选代码度量结果

1.  从**筛选器**列表中，选择的列名称。

2.  在中**Min**，键入要显示的最小值。

3.  在中**最大**，键入要显示的最大值。

4.  单击**应用筛选器**按钮。

5.  若要查看结果详细信息，请展开层次结构树。

## <a name="adding-removing-and-rearranging-data-columns"></a>添加、 删除和重新排列的数据列

您可以添加或删除的结果中的列**代码度量结果**窗口。 此外，以使它们显示在所需的顺序可以重新排列结果列。

### <a name="to-remove-a-column"></a>若要删除某一列

1. 单击**添加/删除列**按钮。

     \- 或-右键单击任何列标题，然后单击**添加/删除列**。

1. 在中**添加/删除列**对话框中，清除该复选框列想要删除，然后单击**确定**。

### <a name="to-add-a-previously-removed-column"></a>若要添加先前删除的列

1. 单击**添加/删除列**按钮。

     \- 或 -

     右键单击任意列标题，然后单击**添加/删除列**。

1. 在中**添加/删除列**对话框框中，选中你想要添加，然后单击的列的复选框**确定**。

### <a name="to-rearrange-columns"></a>若要重新排列列

1. 单击**添加/删除列**按钮。

     \- 或 -

     右键单击任意列标题，然后单击**添加/删除列**。

1. 在中**添加/删除列**对话框框中，选择你想要移动，然后单击向上箭头或向下箭头的列。

1. 当列位于所需的位置时，单击**确定**。

## <a name="copying-data-to-the-clipboard-or-excel"></a>将数据复制到剪贴板或 Excel

可以选择并复制到剪贴板作为文本字符串都包含一行的名称和每个数据列的值为所选的行的代码度量数据。 此外可以单击**在 Microsoft Excel 中打开所选内容**将所有代码度量结果导出到 Excel 电子表格。

## <a name="creating-a-work-item-based-on-code-metric-results"></a>创建基于代码度量结果的工作项

您可以创建[Azure 板](/azure/devops/boards/index)基于工作项会导致**代码度量结果**窗口。 当创建工作项时，Visual Studio 会自动输入中的标题**标题**下的字段和代码度量值数据**历史记录**选项卡。

详细了解 Azure 板的工作项，请参阅[的工作项](/azure/devops/boards/work-items/index)。

### <a name="to-create-a-work-item-based-on-a-result"></a>若要创建基于某一结果的工作项

1.  右键单击结果。

2.  指向**创建工作项**，然后单击你想要创建的工作项类型 (**Bug**，**任务**，依此类推)。

3.  通过填写所有必填字段来完成工作项窗体。

4.  上**文件**菜单上，单击**全部保存**来保存工作项。

### <a name="to-create-a-bug-based-on-a-result"></a>若要创建基于某一结果的 bug

1.  单击以选中它的结果。

2.  单击**创建工作项**按钮。

3.  通过填写所有必填字段来完成工作项窗体。

4.  上**文件**菜单上，单击**全部保存**来保存工作项。

## <a name="see-also"></a>请参阅

- [代码度量值](../code-quality/code-metrics-values.md)
- [如何： 生成代码度量数据](../code-quality/how-to-generate-code-metrics-data.md)