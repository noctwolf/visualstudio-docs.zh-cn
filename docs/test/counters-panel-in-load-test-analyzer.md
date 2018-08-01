---
title: 用于分析 Visual Studio 中负载测试的计数器面板
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, counters panel
ms.assetid: e1a388d7-5d33-4631-931a-5653ac4aefdc
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 2b85d2d20f4400e252cbfd19ea169c7b27b2aecf
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2018
ms.locfileid: "39176874"
---
# <a name="use-the-counters-panel-in-graphs-view-and-tables-view"></a>使用“图”视图和“表”视图中的“计数器”面板

运行负载测试或分析负载测试结果时，可以在负载测试分析器的“图”视图和“表”视图中看到“计数器”面板。 有关详细信息，请参阅[在“图”视图中分析负载测试结果](../test/analyze-load-test-results-in-the-graphs-view.md)、[在“表”视图中分析负载测试结果和错误](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)和[如何：访问负载测试结果以进行分析](../test/how-to-access-load-test-results-for-analysis.md)。

“计数器”面板显示在负载测试期间收集的所有性能计数器的结构化视图。 若要显示或隐藏“计数器”面板，可以选择“负载测试分析器”工具栏上的“显示‘计数器’面板”。

计数器以树结构进行组织，其中叶节点是可以绘图的性能计数器实例。

计数器面板提供以下功能：

-   传达阈值冲突信息。

-   选择计数器进行绘图。

-   在负载测试运行期间收集的所有性能计数器的结构化树视图，其中包含以下主要分支：

    -   **总体：** 包含每个测试代理以及整个负载测试的性能计数器数据汇总。

    -   **方案名称：** 性能计数器树中标记有负载测试方案名称的分支包含与特定负载测试方案关联的所有负载测试计数器实例。 大多数负载测试计数器都嵌套在方案分支中。

         方案分支包含 Web 性能测试节点。 Web 性能测试节点包含页、请求和事务节点。 此结构中的任何叶节点都是可以添加到关系图的性能计数器。

    -   **计算机：** 包含按计算机分组的所有非负载测试计数器实例。 对于与在当前所选测试设置“角色”部分中指定的负载测试控制器关联的每台计算机，计算机分支都包含一个对应节点。 有关详细信息，请参阅[测试控制器和测试代理](configure-test-agents-and-controllers-for-load-tests.md)。

         每个计算机节点都包含从该计算机收集的一组性能计数器类别。 类别包含计数器，而计数器包含性能计数器实例名称。

    -   **错误：** 包含负载测试期间检测到的所有错误。 错误节点包含多个子类别错误节点。 子类别针对不同类型的错误，例如异常和 HTTP 错误。

### <a name="scenario-name-node-in-counters-panel"></a>计数器面板中的方案名称节点

|“计数器”面板|描述|
|-|-|
|![计数器面板的方案名称节点](../test/media/ltest__namenode.png)|1.与负载测试的 Scenario1 关联的所有性能计数器都出现在此节点下。<br />2.某个方案的所有测试都位于该方案节点下。 标签指示测试名称。<br />3.测试节点下的叶节点是计数器实例名称与测试名称相同的负载测试测试用例计数器。<br />4.与 Web 性能测试分支关联的所有负载测试页计数器实例。 在此节点处，此处包含与负载测试的 Scenario1 中 IBuyBrowse Web 性能测试的页 Login GET（报告名称）关联的所有负载测试节奏计数器实例。<br />5.页节点下的子节点是负载测试页计数器。<br />6.与 Web 性能测试关联的所有负载测试请求计数器实例都包含在 Web 性能测试分支中。 在此节点处，此处包含与负载测试的 Scenario1 中 IBuyBrowse Web 性能测试的请求 Login GET（报告名称）关联的所有请求计数器实例。<br />7.请求节点下的叶节点是负载测试请求计数器。<br />8.与 Web 性能测试关联的所有负载测试事务计数器实例都包含在 Web 性能测试分支中。 在此节点处，此处包含与负载测试的 Scenraio1 中 IBuyBrowse Web 性能测试的事务（名为 Transaction1）关联的所有事务计数器实例。<br />9.事务节点下的叶节点是负载测试事务计数器。<br />10.单元测试节点。|

## <a name="tasks"></a>任务

|任务|关联主题|
|-----------|-----------------------|
|**在“图”视图上向图中添加更多性能计数器：** 在“计数器”面板上，可以向图中添加更多性能计数器，从而将不同种类的数据添加到负载测试图中。|-   [如何：在图上添加和删除计数器](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)|
|**分析已超出的在负载测试中指定的任何阈值：**“计数器”面板显示表示已超出阈值的图标，可供添加到表和图中，以供进一步分析。|-   [如何：使用“计数器”面板分析已超出的阈值](../test/analyze-threshold-rule-violations-in-load-tests.md)|
|**分析在负载测试运行期间检测到的任何错误：**“计数器”面板中有错误节点，其中包含可用于向图中添加错误以供进一步分析的错误类别和子类别，如 HTTP 错误。|-   [如何：使用“计数器”面板分析错误](../test/how-to-analyze-errors-using-the-counters-panel.md)|

## <a name="performance-counter-sampling-interval-considerations"></a>性能计数器采样间隔注意事项

基于负载测试的长度，在负载测试运行设置中为“采样率”属性选择一个值。 较小的采样速率（如 5 秒默认值）需要占用负载测试结果数据库中的更多空间。 对于更长的负载测试，增加采样速率会减少收集的数据量。 有关详细信息，请参阅[如何：指定采样率](../test/how-to-specify-the-sample-rate-for-a-load-test.md)。

下面是有关采样速率的一些准则：

|负载测试持续时间|建议的采样速率|
|------------------------|-----------------------------|
|\< 1 小时|5 秒|
|1 - 8 小时|15 秒|
|8 - 24 小时|30 秒|
|> 24 小时|60 秒|

## <a name="considerations-for-including-timing-details-to-collect-percentile-data"></a>添加收集百分比数据所需的计时详细信息的注意事项

负载测试编辑器的运行设置中有一个名为“计时详细信息存储”的属性。 如果启用了“计时详细信息存储”属性，则在负载测试过程中执行各个测试、事务和页所需的时间都存储在负载测试结果储存库中。 这使得 90% 和 95% 的数据显示在负载测试分析器的“测试”、“事务”和“页”表中。

在“运行设置”属性中启用“计时详细信息存储”属性的方法有以下两种：“StatisticsOnly”和“AllIndividualDetails”。 无论采用哪个选项，所有单个测试、页和事务均会计时，且根据单个计时数据来计算百分比数据。 它们的区别是，使用“StatisticsOnly”选项时，在计算完百分比数据之后，将立即从存储库中删除单个计时数据。 删除数据可以减少使用计时详细信息时储存库中所需的空间量。 但是，高级用户可能需要使用 SQL 工具以其他方式来处理计时详细信息数据。 如果是这样，则应使用“AllIndividualDetails”选项，以便计时详细信息数据可用于该处理。 此外，如果将属性设置为“AllIndividualDetails”，可以在负载测试运行结束后，使用负载测试分析器中的“虚拟用户活动”图表来分析虚拟用户活动。 有关详细信息，请参阅[在“详细信息”视图中分析虚拟用户活动](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)。

负载测试结果储存库中存储计时详细信息数据所需的空间可能会非常大，尤其是对于运行时间较长的负载测试。 另外，在负载测试结束时将此数据存储到负载测试结果储存库中所需的时间也较长，因为在负载测试完成执行之前此数据一直存储在负载测试代理上。 负载测试完成时，数据将存储到储存库中。 默认情况下，将启用“计时详细信息存储”属性。 如果这对测试环境来说有问题，则可能需要将“计时详细信息存储”设置为“无”。

有关详细信息，请参阅[如何：指定“计时详细信息存储”属性](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md)。

## <a name="see-also"></a>请参阅

- [分析负载测试结果](../test/analyze-load-test-results-using-the-load-test-analyzer.md)