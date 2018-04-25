---
title: 在 Visual Studio 中比较负载测试结果 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, reporting
- load tests, results
ms.assetid: 31874114-459a-45d5-9f8b-2ea503627db8
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: fe8eefff69532aa843f619518c59067b31619e8f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="reporting-load-tests-results-for-test-comparisons-or-trend-analysis"></a>报告负载测试结果以比较测试或进行趋势分析

可以生成基于两个或更多测试结果的 Microsoft Excel 负载测试报告。 负载测试报告分为两种：

- 运行比较 &mdash; 这种报告实际上是两个报告，它们使用表和条形图并排显示比较数据。

- 趋势 &mdash; 可对两个或更多报告生成趋势分析。 结果是使用折线图显示的。

这两种报告都可用于与利益干系人共享性能数据，传达系统的整体性能和运行状况是变好还是变差。

报告定义存储在负载测试数据库中。 保存报告后，报告定义保存在数据库中，以后可以重用。

此外，可将电子表格文件与利益干系人共享，以便利益干系人不必连接到数据库就可以查看报告。

> [!NOTE]
> 如果向负载测试中添加注释，注释将出现在 Excel 报告中。 有关详细信息，请参阅[如何：在分析完成的负载测试时添加注释](../test/how-to-add-comments-on-a-completed-load-test.md)。

## <a name="tasks"></a>任务

|任务|关联主题|
|-----------|-----------------------|
|**创建性能和压力报告：**可使用 Microsoft Excel 创建有关负载测试和 Web 性能测试的报告。|- [如何：使用 Microsoft Excel 创建负载测试性能报告](../test/how-to-create-load-test-performance-reports-using-microsoft-excel.md)|
|**使用 Microsoft Word 手动创建性能和压力报告：**可以通过将摘要、表和关系图数据复制并粘贴到 Microsoft Word 文档中，手动创建有关负载测试和 Web 性能测试的报告。|- [如何：使用 Microsoft Word 手动创建负载测试性能报告](../test/how-to-manually-create-a-load-test-performance-report-using-microsoft-word.md)|

## <a name="see-also"></a>请参阅

- [分析负载测试结果](../test/analyze-load-test-results-using-the-load-test-analyzer.md)