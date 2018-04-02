---
title: 为 Visual Studio 中的负载测试收集虚拟用户的完整详细信息 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, virtual user activity chart, configuring
- virtual user activity chart, configuring
ms.assetid: cb22e43b-af4d-4e09-9389-3c3fa00786f7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: b410c91ff2b6c57b86c7fe377df4bf31173f9384
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-configure-load-tests-to-collect-full-details-to-enable-virtual-user-activity-in-test-results"></a>如何：将负载测试配置为收集完整详细信息，以便在测试结果中启用虚拟用户活动

若要对负载测试使用虚拟用户活动图，必须将负载测试配置为收集完整详细信息。 若要为负载测试配置此功能，请为与负载测试关联的“计时详细信息存储”属性选择“所有的详细信息”设置。 在此模式中，负载测试将收集有关每个测试、页面和事务的详细信息。

 如果你要从早期版本的 Visual Studio 负载测试升级项目，请使用以下过程中的步骤启用完整详细信息集合。

 “计时详细信息存储”属性的“所有的详细信息”设置可以设置为以下任一选项：

-   **所有的详细信息：**收集并存储测试过程中发出的每个测试、事务和页面的单独计时数据。

    > [!NOTE]
    > 必须选择“所有的详细信息”选项才能启用负载测试结果中的虚拟用户数据信息。

-   **无：**不收集任何单独计时详细信息。 但是，平均值仍然可用。

-   **仅统计信息：**存储单独的计时数据，但仅作为百分比数据。 此选项节省空间资源。

## <a name="to-configure-the-timing-details-storage-property-in-a-load-test"></a>配置负载测试中的计时详细信息存储属性

1.  在负载测试编辑器中打开一个负载测试。

2.  展开负载测试中的“运行设置”节点。

3.  选择要配置的运行设置，例如“Run Settings1[Active]”。

4.  打开“属性”窗口。 在“视图”菜单上选择“属性”窗口。

5.  在“结果”类别下，选择“计时详细信息存储”属性，然后选择“所有的详细信息”。

     为“计时详细信息存储”属性配置“所有的详细信息”设置之后，可以运行负载测试并查看虚拟用户活动图。 有关详细信息，请参阅[如何：分析虚拟用户在负载测试期间的操作](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md)。

## <a name="see-also"></a>请参阅

- [在详细信息视图中分析虚拟用户活动](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [演练：使用虚拟用户活动图隔离问题](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)