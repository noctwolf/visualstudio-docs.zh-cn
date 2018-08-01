---
title: Visual Studio 中负载测试的阈值冲突
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, threshold violations
ms.assetid: 0126d7b7-0538-4ea9-9046-6556654b3b9d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: cb64626034c8c9bf03875385a80ebc417bf05dcb
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204058"
---
# <a name="how-to-analyze-threshold-violations-using-the-counters-panel-in-load-test-analyzer"></a>如何：使用负载测试分析器中的计数器面板分析阈值冲突

在运行负载测试或分析负载测试结果时，在“负载测试分析器”的关系图视图和表视图中可以看见“计数器”面板。 请参阅[在关系图视图中分析负载测试结果](../test/analyze-load-test-results-in-the-graphs-view.md)、[在表视图中分析负载测试结果](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)和[如何：访问负载测试结果以进行分析](../test/how-to-access-load-test-results-for-analysis.md)。

 阈值冲突与特定性能计数器关联，并指示性能计数器已超过或低于设置的阈值。 “计数器”面板中的图标表示阈值冲突。

 ![计数器面板的计算机节点](../test/media/ltest_compnode.png)

 阈值冲突的图标会从失败的计数器所在的树节点传播到根。 该图标提醒用户注意由于树未展开而可能在树中不可见的计数器上发生的冲突。 可以在上图的“计数器”面板的“计算机”节点中看到图标示例。

 该图标可以为如下所述的几种图标之一：

 ![没有阈值冲突](../test/media/icon_ltest_1.gif) 无示阈值冲突。

 ![上次间隔中出现严重阈值冲突](../test/media/icon_ltest_2.gif) 在上一个间隔内发生严重阈值冲突。

 ![前一间隔中出现严重阈值冲突](../test/media/icon_ltest_3.gif) 在前面的某个间隔内发生严重阈值冲突。

 ![上次间隔中出现警告阈值冲突](../test/media/icon_ltest_4.gif) 在上一个间隔内发生警告阈值冲突。

 ![前一间隔中出现警告阈值冲突](../test/media/icon_ltest_5.gif) 在前面的某个间隔内发生警告阈值冲突。

## <a name="to-analyze-threshold-violations-in-the-counters-panel"></a>分析计数器面板中的阈值冲突

1.  在完成加载测试或加载测试结果后，在负载测试分析器的工具栏中，选择“关系图”或“表”。

     “计数器”面板显示在关系图视图或表视图中。

2.  如果看不到“计数器”面板，请选择工具栏上的“显示计数器面板”。

     包含阈值冲突的任何节点都将包含上面所列的图标之一。

3.  展开包含阈值图标的节点，例如“计算机”节点（如前面标题为“计数器面板中具有阈值冲突的‘计算机’节点”的图中所示）。 继续展开节点，直至到达具有阈值冲突的性能计数器。 例如，上图显示了“Microsoft 虚拟机故障总线网络适配器”的失败实例。

4.  （可选）右击具有阈值冲突的性能计数器，然后选择以下选项之一：

    -   **在关系图上显示计数器**：在“关系图”视图中，在选定的关系图上添加性能计数器并突出显示。 有关详细信息，请参阅[如何：在关系图上添加和删除计数器](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)。

        > [!NOTE]
        > 阈值冲突图标也可以在“关系图”视图中的关系图上显示。 阈值图标显示在关系图上发生阈值冲突的数据点旁边。 为此，请选择工具栏中的“显示图例”下拉列表并选择“在关系图上显示阈值冲突”。

    -   **在图例上显示计数器**：在图例中，添加并选中性能计数器。 有关详细信息，请参阅[使用关系图视图图例分析负载测试](../test/use-the-graphs-view-legend-to-analyze-load-tests.md)。

    -   **添加关系图**：

    1.  随即显示“请输入关系图名称”对话框。

    2.  在“关系图名称”文本框中，键入新关系图的名称，然后选择“确定”。

    3.  （可选）再次右击性能计数器，然后选择“在关系图上显示计数器”。

         有关详细信息，请参阅[如何：创建自定义关系图](../test/how-to-create-custom-graphs-in-load-test-results.md)。

5.  （可选）如果你正在分析完整的负载测试结果中的阈值冲突，可考虑在“关系图”视图中使用缩放功能。 有关详细信息，请参阅[如何：放大关系图的区域](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)。

    > [!TIP]
    > 如果在负载测试运行期间检测到任何阈值冲突，则会在“负载测试分析器”的状态栏中显示名为“阈值冲突”的链接（包括冲突数）。 选择该链接可在“表”视图的“阈值”表中显示所有阈值冲突。

## <a name="see-also"></a>请参阅

- [在关系图视图和表视图中使用计数器面板](../test/counters-panel-in-load-test-analyzer.md)
- [分析负载测试结果](../test/analyze-load-test-results-using-the-load-test-analyzer.md)