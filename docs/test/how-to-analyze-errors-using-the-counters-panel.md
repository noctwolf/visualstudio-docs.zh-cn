---
title: 在 Visual Studio 中使用计数器面板分析负载测试错误 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Load Test Analyzer, counters panel
ms.assetid: 981b4f1e-505a-4078-a06d-58ae17d996b4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 055925fd626e03df6e80fe02647fc2c1ca67d6ad
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-analyze-errors-using-the-counters-panel"></a>如何：使用计数器面板分析错误

在运行负载测试或分析负载测试结果时，在负载测试分析器的关系图视图和表视图中可以看见计数器面板。 有关详细信息，请参阅[在关系图视图中分析负载测试结果](../test/analyze-load-test-results-in-the-graphs-view.md)、[在表视图中分析负载测试结果和错误](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)和[如何：访问负载测试结果以进行分析](../test/how-to-access-load-test-results-for-analysis.md)。

 计数器面板中的“错误”节点包含负载测试期间检测到的所有错误。 错误节点包含特定于不同类型错误的若干个子类别错误节点。 例如，“异常”和“HTTP 错误”。

 ![计数器面板的错误节点](../test/media/ltest_errornode.png "LTest_ErrorNode")

## <a name="to-analyze-errors-in-the-counters-panel"></a>在计数器面板中分析错误

1.  在完成加载测试或加载测试结果后，在负载测试分析器的工具栏中，选择“关系图”或“表”。

     “计数器”面板显示在关系图视图或表视图中。

2.  如果看不到计数器面板，请选择工具栏上的“显示计数器面板”。

3.  展开“错误”，然后选择要分析的错误类别或错误子类别。

4.  右击相应的错误，然后选择以下选项之一：

    -   **在关系图上显示计数器**：在关系图视图中，错误将添加到所选关系图上并突出显示。 有关详细信息，请参阅[如何：在关系图上添加和删除计数器](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)。

    -   **在图例上显示计数器**：错误将添加到图例中并处于选中状态。 有关详细信息，请参阅[使用关系图视图图例分析负载测试](../test/use-the-graphs-view-legend-to-analyze-load-tests.md)。

    -   **添加关系图**：

    1.  随即显示“请输入关系图名称”对话框。

    2.  在“关系图名称”文本框中，键入新关系图的名称，然后选择“确定”。

    3.  （可选）再次右击相应的错误，然后选择“在关系图上显示计数器”。

         有关详细信息，请参阅[如何：创建自定义关系图](../test/how-to-create-custom-graphs-in-load-test-results.md)。

5.  （可选）如果要分析完成的测试结果中的错误，请考虑在关系图中使用缩放功能。 有关详细信息，请参阅[如何：放大关系图的区域](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)。

    > [!TIP]
    > 如果在负载测试运行期间检测到任何错误，则将在负载测试分析器的状态栏中显示错误链接，其中包括所找到的错误数。 选择该链接可在表视图的“错误”表中显示所有错误。

## <a name="see-also"></a>请参阅

- [在关系图视图和表视图中使用计数器面板](../test/counters-panel-in-load-test-analyzer.md)
- [分析负载测试结果](../test/analyze-load-test-results-using-the-load-test-analyzer.md)