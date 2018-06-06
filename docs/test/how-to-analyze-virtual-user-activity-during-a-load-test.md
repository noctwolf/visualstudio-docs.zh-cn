---
title: 在 Visual Studio 中分析虚拟用户活动以进行负载测试
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- virtual user activity chart, viewing
ms.assetid: 8bda19b3-91c1-4daf-b6c7-09108bddadff
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: f7da7f881cf70ebfdafb3dbaaf2821471327fa81
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751229"
---
# <a name="how-to-analyze-what-virtual-users-are-doing-during-a-load-test-using-the-virtual-user-activity-chart"></a>如何：使用虚拟用户活动图分析虚拟用户在负载测试期间的操作

可使用虚拟用户活动图查看与负载测试关联的虚拟用户活动。 图中的每一行代表一个虚拟用户。 虚拟用户活动图显示每个虚拟用户在测试期间所执行的操作。 可以查看用户活动的模式和负载模式、关联失败的或速度缓慢的测试，还可以查看具有其他虚拟用户活动的请求。 只有在运行完负载测试之后，虚拟用户活动图才可用。

下面的过程演示如何查看虚拟用户活动图、如何调查特定的用户活动以及如何使用筛选。

## <a name="to-view-the-virtual-user-activity-chart-in-your-load-test-results"></a>在负载测试结果中查看虚拟用户活动图

1.  若要查看虚拟用户数据，必须首先为与负载测试关联的“计时详细信息存储”属性配置“所有的详细信息”设置。 然后运行负载测试。 有关详细信息，请参阅[如何：配置“收集完整详细信息”以启用虚拟用户活动图表](../test/how-to-configure-load-tests-to-collect-full-details.md)。

2.  运行完负载测试之后，将显示测试结果摘要页。 选择工具栏上的“用户详细信息”按钮。

     或

     通过选择工具栏上的“关系图”按钮打开关系图视图。 右键单击某个关系图，然后选择“转到用户详细信息”。

     如果使用此选项，则虚拟用户活动图将自动缩放到你右击的测试部分。 例如，如果鼠标指针位于大约 30 秒标记处，则详细信息视图将在虚拟用户活动图底部的“缩放到时间段”工具中显示大约 30 秒标记部分。

     接下来，您便可以在虚拟用户活动图中调查特定用户活动详细信息了。

## <a name="to-investigate-a-specific-users-activity-in-the-virtual-user-activity-chart"></a>在虚拟用户活动图中调查特定用户活动

1.  使用虚拟用户活动图底部的“缩放到时间段“工具在图上选择要调查特定用户详细信息的区域。

2.  将鼠标指针悬停在图中的某个详细信息上。 请注意，在工具提示中将显示以下信息：

    -   **用户 ID**

    -   **方案**

    -   **测试**

    -   **URL**（不显示在测试或事务中）

    -   **结果**

    -   **浏览器**（不显示在测试或事务中）

    -   **Network**

    -   **开始时间**

    -   **持续时间**

    -   **代理**

    -   **测试日志**（测试日志的链接）

        > [!NOTE]
        > 为了帮助调试应用程序，如果选择“测试日志”链接，将会打开与该日志关联的 Web 测试结果或单元测试结果。

     接下来，您便可以使用虚拟用户活动图中可用的筛选和突出显示操作了。

## <a name="to-use-filtering-options-in-the-virtual-user-activity-chart"></a>在虚拟用户活动图中使用筛选选项

1.  在详细信息图例中，使用下拉列表选择“测试”、“页面”或“事务”。

     **详细信息图例面板**

     ![详细信息图例面板](../test/media/ltest_detailslegend.png)

2.  选中或清除与负载测试关联的错误、日志、测试、搜索和 aspx 页面对应的复选框。

     虚拟用户活动图会相应地更新。

     虚拟用户活动图提供基于多种不同条件来筛选测试、页面和事务的功能。 可以从视图中移除某些测试或移除所有成功的测试，或者移除因某些故障而失败的测试。 还可以移除没有日志的所有测试。

     例如，可以选择“(突出显示错误)”选项，这将在图表中以红色显示所有错误。 也可以选择“(突出显示含日志的结果)”选项，这将在图表中以绿色显示含有日志的所有测试结果。

     **筛选结果面板**

     ![筛选结果面板](../test/media/ltest_filterresults.png)

3.  在“筛选结果”中，选中或清除与以下筛选选项对应的复选框：

    -   “仅显示含日志的结果”仅显示具有关联测试日志的测试结果。

    -   “显示成功结果”显示成功的结果。

    -   “显示包含错误的结果”显示包含可以帮助进行调试的错误的结果。

        > [!NOTE]
        > 通过选择 Web 性能测试结果查看器工具栏中的“表”按钮，可以进一步调查“显示包含错误的结果”节点下列出的错误类型列表。 有关详细信息，请参阅[在表视图中分析负载测试结果和错误](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)。

     虚拟用户活动图会相应地更新。

## <a name="see-also"></a>请参阅

- [在详细信息视图中分析虚拟用户活动](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [演练：使用虚拟用户活动图隔离问题](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)