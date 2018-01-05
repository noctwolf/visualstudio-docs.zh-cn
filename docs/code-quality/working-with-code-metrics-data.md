---
title: "代码度量结果 Visual Studio 中的 |Microsoft 文档"
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c259a1d303c741d4e36af46250073b0378a65f8b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="working-with-code-metrics-data"></a>使用代码度量数据

**代码度量结果**窗口显示生成的代码度量值分析的数据。 有关代码度量数据值的详细信息，请参阅[代码度量值](../code-quality/code-metrics-values.md)。

## <a name="displaying-code-metrics-results"></a>显示代码度量结果

**代码度量结果**生成代码度量结果时，会自动显示窗口。 你还可以在任何时候显示窗口。

### <a name="to-display-the-code-metrics-results-window"></a>若要显示代码度量结果窗口

- 上**分析**菜单上，选择**Windows** > **代码度量结果**。

   \- 或 -

- 上**视图**菜单上，选择**其他窗口** > **代码度量结果**。

   **代码度量结果**显示窗口，即使不包含任何结果。

### <a name="to-view-code-metrics-details"></a>若要查看代码度量值详细信息

如果生成了代码度量结果，展开的树中**层次结构**列。

## <a name="filtering-code-metrics-results"></a>筛选代码度量结果

您可以筛选结果中显示**代码度量结果**窗口通过使用在顶部的工具栏。 例如，你可能想要查看具有可维护性指数低于 65 结果。

**筛选器**下拉框中包含的结果列的名称。 定义筛选器后，则将它添加到并进行缩进列表的底部。 此列表可以包含 10 个最新的筛选器定义。

### <a name="to-filter-the-code-metrics-results"></a>若要筛选代码度量结果

1.  从**筛选器**列表中，选择的列名称。

2.  在**Min**，键入要显示的最小值。

3.  在**最大**，键入要显示的最大值。

4.  单击**应用筛选器**按钮。

5.  若要查看结果详细信息，请展开层次结构树。

## <a name="adding-removing-and-rearranging-data-columns"></a>添加、 移除和重新排列的数据列

你可以添加或删除结果中的列**代码度量结果**窗口。 以便它们显示在所需的顺序，此外，可以重新排列结果列。

### <a name="to-remove-a-column"></a>若要删除列

1. 单击**添加/删除列**按钮。

     \-或-右键单击任何列标题，然后单击**添加/删除列**。

1. 在**添加/删除列**对话框中，清除该复选框为列你想要删除，然后单击**确定**。

### <a name="to-add-a-previously-removed-column"></a>若要添加先前删除的列

1. 单击**添加/删除列**按钮。

     \- 或 -

     右键单击任何列标题，然后单击**添加/删除列**。

1. 在**添加/删除列**对话框框中，选中你想要添加，然后单击的列的复选框**确定**。

### <a name="to-rearrange-columns"></a>若要重新排列列

1. 单击**添加/删除列**按钮。

     \- 或 -

     右键单击任何列标题，然后单击**添加/删除列**。

1. 在**添加/删除列**对话框框中，选择你想要移动，然后单击向上箭头或向下箭头的列。

1. 当列位于所需的位置时，单击**确定**。

## <a name="copying-data-to-the-clipboard-or-excel"></a>将数据复制到剪贴板或 Excel

你可以选择并复制到剪贴板的代码度量数据的所选的行作为一个文本字符串，包含一个行的名称和每个数据列的值。 您也可以单击**在 Microsoft Excel 中打开所选内容**将所有代码度量结果导出到 Excel 电子表格。

## <a name="creating-a-work-item-based-on-code-metric-results"></a>创建基于代码度量结果的工作项

你可以创建[Visual Studio Team Services (VSTS)](/vsts/index)基于工作项导致**代码度量结果**窗口。 当创建工作项后时，Visual Studio 将自动进入中的标题**标题**下的字段和代码度量值数据**历史记录**选项卡。

VSTS 有关详细信息的工作项，请参阅[工作项 (VSTS)](/vsts/work/work-items/index)。

### <a name="to-create-a-work-item-based-on-a-result"></a>若要创建根据结果的工作项

1.  右键单击结果。

2.  指向**创建工作项**，然后单击你想要创建的工作项类型 (**Bug**，**任务**，依此类推)。

3.  通过填写所有必填字段中完成的工作项窗体。

4.  上**文件**菜单上，单击**保存所有**保存工作项。

### <a name="to-create-a-bug-based-on-a-result"></a>若要创建根据结果的 bug

1.  单击以选中它的结果。

2.  单击**创建工作项**按钮。

3.  通过填写所有必填字段中完成的工作项窗体。

4.  上**文件**菜单上，单击**保存所有**保存工作项。

## <a name="see-also"></a>请参阅

[代码度量值](../code-quality/code-metrics-values.md)  
[如何：生成代码度量数据](../code-quality/how-to-generate-code-metrics-data.md)