---
title: 在 Visual Studio 中保存负载测试日志
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, logging
ms.assetid: 9ac88d8a-4777-462c-aa0e-244dadb2cfd1
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 4114a938f643cee629311a72aec72f94cfcd2fc4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-specify-how-frequently-test-logs-are-saved-using-the-load-test-editor"></a>如何：使用负载测试编辑器指定保存测试日志的频率

在用“新建负载测试向导”创建负载测试之后，可以使用“负载测试编辑器”更改负载测试属性，以满足你的测试需求和目标。 有关详细信息，请参阅[演练：创建和运行负载测试](../test/walkthrough-create-and-run-a-load-test.md)。

> [!NOTE]
> 有关运行设置属性及其说明的完整列表，请参见[负载测试运行设置属性](../test/load-test-run-settings-properties.md)。

通过使用负载测试编辑器在“属性”窗口中更改“为已完成测试保存日志的频率”属性，可以指定负载测试中保存测试日志的频率。

## <a name="to-specify-the-frequency-for-saving-the-test-log-in-a-load-test"></a>指定负载测试中保存测试日志的频率

1.  打开一个负载测试。

     此时将显示负载测试编辑器。 其中显示负载测试树。

2.  在负载测试树的“运行设置”文件夹中，选择要为其指定保存测试日志的频率的运行设置节点。

3.  在“视图”菜单上选择“属性窗口”。

     该方案的类别和属性将显示在“属性”窗口中。

4.  在“为已完成测试保存日志的频率”属性的文本框中，键入一个数字以指示将写入测试日志的频率。 该数字指示将测试保存到测试日志的频率为每达到输入的测试数即保存一次。 例如，如果输入的值为 10，则指定第 10 个、20 个、30 个等测试将写入测试日志。

    > [!NOTE]
    > 如果“为已完成测试保存日志的频率”属性使用值 0，则指定不保存测试日志。

5.  更改完此属性后，请选择“文件”菜单上的“保存”。

     可以使用负载测试分析器的表视图来查看保存在日志中的数据。 有关详细信息，请参阅[在表视图中分析负载测试结果和错误](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)。

## <a name="see-also"></a>请参阅

- [编辑负载测试方案](../test/edit-load-test-scenarios.md)
- [演练：创建和运行负载测试](../test/walkthrough-create-and-run-a-load-test.md)
- [编辑负载测试方案](../test/edit-load-test-scenarios.md)
- [如何：指定是否将测试失败保存到测试日志中](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)
- [如何：配置“收集完整详细信息”以启用虚拟用户活动图表](../test/how-to-configure-load-tests-to-collect-full-details.md)