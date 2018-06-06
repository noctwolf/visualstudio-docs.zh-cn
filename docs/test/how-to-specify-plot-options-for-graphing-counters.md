---
title: Visual Studio 中负载测试的关系图计数器的绘图选项
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, graphing counters
ms.assetid: 1969c20b-e0eb-48f6-a49f-a9090cd86008
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 7a5f87a83b8c743ae869a700618051e07c8c2e75
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750917"
---
# <a name="how-to-specify-plot-options-for-graphing-counters"></a>如何：为绘图计数器指定绘图选项

使用“绘图选项”对话框，可以更改关系图上所绘制的计数器的颜色和线型。 也可以将范围固定为特定值，或将范围设置为基于采样的数据自动进行调整。

![“绘图选项”对话框](../test/media/ltest_plotoptions.png)

## <a name="to-specify-plotting-options-for-graphs"></a>指定关系图的绘图选项

1.  在负载测试分析器中，选择负载测试工具栏上的“关系图”。

     这将在关系图视图中显示负载测试结果。

2.  在图例或关系图中，右键单击要对其更改绘图选项的性能计数器所在的行或当前绘图线，然后选择“绘图选项”。

     显示“绘图选项”对话框。

3.  使用“颜色”下拉列表，选择绘制性能计数器时要使用的颜色。

4.  使用“样式”下拉列表，选择绘制性能计数器时要使用的样式。

5.  执行下列操作之一：

     选择“自动调整范围”（默认）

     \- 或 -

     清除“自动调整范围”，然后使用“范围”下拉列表指定绘制性能计数器时要使用的范围。

6.  选择 **“确定”**。

     已更改其选项的性能计数器显示在发生了您指定的更改的关系图中。

## <a name="see-also"></a>请参阅

- [在关系图视图中分析负载测试结果](../test/analyze-load-test-results-in-the-graphs-view.md)
- [如何：创建自定义关系图](../test/how-to-create-custom-graphs-in-load-test-results.md)
- [在关系图视图中分析负载测试结果](../test/analyze-load-test-results-in-the-graphs-view.md)