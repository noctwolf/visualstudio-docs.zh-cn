---
title: 在 Visual Studio 的负载测试中“对节奏延迟应用分布”| Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, test mix model
ms.assetid: ae8b35f9-d465-4d72-8d7d-7b56ae6ffd22
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 5140a3ca9cb8274a9b6d9f74260adadfed6201ad
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-apply-distribution-to-pacing-delay-when-using-a-user-pace-test-mix-model"></a>如何：在使用用户节奏测试组合模型时对节奏延迟应用分布

在使用“新建负载测试向导”创建负载测试后，可以使用“负载测试编辑器”更改方案属性，以满足测试需求和目标。

可通过“属性”窗口设置“对节奏延迟应用分布”属性。 可通过负载测试编辑器修改负载测试方案属性。

> [!NOTE]
> “对节奏延迟应用分布”属性仅适用于基于用户节奏配置负载测试组合的情况。 有关详细信息，请参阅[编辑测试组合模型以指定运行测试的虚拟用户的概率](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)。

“对节奏延迟应用分布”的值可以设置为 true 或 false：

-   **True**：方案将应用“编辑测试组合”对话框的“每个用户每小时的测试数”列中的值指定的常规统计分布延迟。 有关详细信息，请参阅[编辑测试组合模型以指定运行测试的虚拟用户的概率](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)。

     例如，假定你将测试的“编辑测试组合”对话框中的“每个用户每小时的测试数”值设置为每小时 2 个测试。 如果“对节奏延迟应用分布”属性设置为“True”，则会将常规统计分布应用于测试之间的等待时间。 用户每小时仍将运行 2 个测试，但是两次测试之间不一定要有 30 分钟的延迟。 第一个测试可以在 4 分钟后运行，第二个测试可以在 45 分钟后运行。

-   **False**：测试将以你为“编辑测试组合”对话框的“每个用户每小时的测试数”列中的值指定的节奏运行。 有关详细信息，请参阅[编辑测试组合模型以指定运行测试的虚拟用户的概率](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)。

     例如，假定你将测试的“编辑测试组合”对话框中的“每个用户每小时的测试数”值设置为每小时 2 个测试。 如果“对节奏延迟应用分布”属性设置为“False”，则测试运行时没有机动时间。 测试的运行间隔将为 30 分钟。 这样可以确保每小时执行 2 个测试。

## <a name="to-specify-the-apply-distribution-to-pacing-delay-property-setting-for-a-scenario"></a>为方案指定“对节奏延迟应用分布”属性设置

1.  打开一个负载测试。

     “负载测试编辑器”随即显示。 其中显示负载测试树。

2.  在负载测试树的“方案”文件夹中，选择要为其指定所用代理的方案节点。

3.  在“视图”菜单上选择“属性”窗口。

     该方案的类别和属性将显示在“属性”窗口中。

4.  在“对节奏延迟应用分布”的属性值中，选择“True”或“False”。

5.  更改属性后，在“文件”菜单上选择“保存”。 然后，可使用新的“对节奏延迟应用分布”值运行负载测试。

## <a name="see-also"></a>请参阅

- [编辑负载测试方案](../test/edit-load-test-scenarios.md)
- [演练：创建和运行负载测试](../test/walkthrough-create-and-run-a-load-test.md)
- [测试控制器和测试代理](configure-test-agents-and-controllers-for-load-tests.md)
- [负载测试方案属性](../test/load-test-scenario-properties.md)