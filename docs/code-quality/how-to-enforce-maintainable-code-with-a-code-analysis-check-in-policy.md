---
title: "如何： 使用代码分析签入策略强制实现代码 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code analysis, check-in policies
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 80f3d2385fa1023637081b787c8d938ae42f79b4
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy"></a>如何： 使用代码分析签入策略强制实现代码

开发人员可以使用代码度量工具来测量的复杂性和可维护性其代码，但不是能作为签入策略的一部分中调用代码度量值。 但是，可以启用代码分析规则，验证你的代码符合代码度量值标准，并强制实施通过签入策略规则。 有关代码度量值的详细信息，请参阅[代码度量值](../code-quality/code-metrics-values.md)。

你可以启用的继承深度、 类耦合、 可维护性指数和复杂性规则来借助代码分析签入策略强制实现代码。 所有四个。 这些规则在代码分析策略编辑器中"可维护性规则"类别下都找到。

Team foundation 版本控制的管理员可以将代码分析可维护性规则添加到的签入策略要求。 这些签入策略需要开发人员运行代码分析在启动签入前根据这些规则的更改。

## <a name="to-open-the-code-analysis-policy-editor"></a>若要打开代码分析策略编辑器

1.在**团队资源管理器**，右键单击团队项目，单击**团队项目设置**，然后单击**源代码管理**。

     The **Source Control** dialog box appears.

2.在**签入策略**卡，然后单击**添加**。

     The **Add Check-in Policy** dialog box appears.

3.在**签入策略**列表中，选择**代码分析**复选框，并依次**确定**。

     The **Code Analysis Policy Editor** dialog box appears.

## <a name="to-enable-code-analysis-maintainability-rules"></a>若要启用代码分析可维护性规则

1.在**代码分析策略编辑器**对话框中，在**规则设置**，展开**可维护性规则**节点。

2.选择以下的规则所对应的复选框：

    -   继承深度： **CA1501 AvoidExcessiveInheritance** -阈值： 在 5 个以上的层深度警告

    -   复杂性： **CA1502 AvoidExcessiveComplexity** -阈值： 多个 25 处出现警告

    -   可维护性指数： **CA1505 AvoidUnmaintainableCode** -阈值： 少于 20 处出现警告

    -   类耦合： **CA1506 AvoidExcessiveClassCoupling** -阈值： 在多个类的 80 和多个方法的 30 警告

    此外，如果你想违反规则时阻止成功生成，则选择**将警告视为错误**规则说明旁边的复选框。

3.单击**确定**。 现在，新签入策略应用到以后进行签入时。

## <a name="see-also"></a>请参阅

[代码度量值](../code-quality/code-metrics-values.md)
[创建和使用代码分析签入策略](../code-quality/creating-and-using-code-analysis-check-in-policies.md)