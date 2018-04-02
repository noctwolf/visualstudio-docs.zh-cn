---
title: 将计算机标记添加到用于 Visual Studio 中负载测试的计数器集映射 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, counter set mappings, computer tags
ms.assetid: f52a73e1-036a-4b28-a6c8-848284bf4488
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 70f3f2c58974478b17c78c3de4014a1921accd76
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-add-computer-tags-to-counter-set-mappings-using-the-load-test-editor"></a>如何：使用负载测试编辑器将计算机标记添加到计数器集映射中

通过计算机标记可以用很容易识别的名称来标识计算机。 在负载测试编辑器中，这些标记会显示在树的“计数器集映射”节点中。 更重要的是，这些标记可显示在 Excel 报表中，从而帮助利益干系人标识计算机在负载测试中所具有的角色。 例如，“Web Server1 in lab2”或“SQL Server2 in Phoenix office”。 有关详细信息，请参阅[报告负载测试结果以比较测试或进行趋势分析](../test/compare-load-test-results.md)。

## <a name="to-add-a-tag-to-a-computer"></a>向计算机添加标记

1.  打开一个负载测试。

2.  选择“管理计数器集”按钮。

     - 或 -

     右击负载测试树中的“计数器集”文件夹，然后选择“管理计数器集”。

     随即显示“管理计数器集”对话框。

3.  （可选）在“选定的计算机和计数器集将添加到以下运行设置下”列表框中，选择其他运行设置。

    > [!NOTE]
    > 这仅适用于负载测试中具有多个运行设置时。

4.  在“要监视的计算机和计数器集”下，选择要将标记应用到的计算机。

    > [!NOTE]
    > 有关如何添加计算机的详细信息，请参阅[如何：管理计数器集](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)。

5.  在“计算机标记”文本框中，键入要与计算机关联的标记。 例如，“TestMachine12 in lab3”。

6.  选择 **“确定”**。

## <a name="see-also"></a>请参阅

- [分析阈值规则冲突](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [分析负载测试结果](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [为负载测试中的计算机指定计数器集和阈值规则](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [如何：管理计数器集](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)