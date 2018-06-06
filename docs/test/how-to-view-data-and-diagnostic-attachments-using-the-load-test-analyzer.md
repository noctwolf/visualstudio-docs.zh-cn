---
title: 在 Visual Studio 中查看用于负载测试的数据和诊断附件
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, data and diagnostics attachments
ms.assetid: 73309bdd-437a-4eb0-88c8-702c3e24b9b0
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 525f4a1d11cd4026410baf696b4593daf2595e12
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751360"
---
# <a name="how-to-view-data-and-diagnostic-attachments-using-the-load-test-analyzer"></a>如何：使用负载测试分析器查看数据和诊断附件

运行负载测试前，可以选择用于指定要使用的诊断和数据适配器的测试设置。 负载测试完成后，可使用负载测试分析器在分析结果时查看这些诊断和数据适配器的详细信息。 若要查看数据和诊断适配器详细信息，请选择负载测试分析器工具栏上的“查看数据和诊断附件”按钮。 例如，如果负载测试在测试设置中配置了系统信息适配器，则可以查看在运行负载测试时使用的计算机的系统信息。

![“选择诊断数据适配器附件”对话框](../test/media/load_adapterdialog.png)

另一个示例是一个在测试设置中包含 IntelliTrace 适配器的负载测试。 使用 IntelliTrace 适配器，可以打开“IntelliTrace 摘要”页。

![IntelliTrace 摘要](../test/media/load_intellitrace.png)

有关详细信息，请参阅[使用测试设置来收集诊断信息](../test/collect-diagnostic-information-using-test-settings.md)和[收集 IntelliTrace 数据](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md)。

## <a name="to-view-data-and-diagnostic-attachments-in-a-load-test-from-the-load-test-analyzer"></a>从负载测试分析器查看负载测试中的数据和诊断附件

1.  负载测试完成后或打开负载测试结果后，在负载测试分析器的工具栏中，选择“查看数据和诊断附件”。

     将显示“选择诊断数据适配器”对话框。

2.  选择要分析的诊断数据适配器附件，然后选择“确定”。

## <a name="see-also"></a>请参阅

- [分析负载测试结果](../test/analyze-load-test-results-using-the-load-test-analyzer.md)