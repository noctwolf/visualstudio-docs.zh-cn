---
title: "如何： 启用和禁用托管代码的完整解决方案分析 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- full solution analysis
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-code-analysis
ms.workload:
- dotnet
ms.openlocfilehash: 64b541093aaf1a710976c0f53a3214b5d2a47e0d
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-enable-and-disable-full-solution-analysis-for-managed-code"></a>如何： 启用和禁用托管代码的完整解决方案分析

*完整解决方案分析*是关闭的 Visual Studio 功能，使你可以查看仅在你的解决方案中打开的 Visual C# 或 Visual Basic 文件中的代码分析问题或还在代码中的文件。 默认情况下，完整解决方案分析适用于 Visual Basic 启用和禁用对于 Visual C#。

尽管能够看到所有文件中的所有问题很有用，它可以让人分散注意力。 它还可以慢速的 Visual Studio 下如果你的解决方案是非常大，或具有大量的文件。 若要限制显示的问题数和改进 Visual Studio 性能，你可以禁用完整解决方案分析。 如有必要，您便可以轻松地重新启用此功能。

## <a name="to-toggle-full-solution-analysis"></a>若要切换完整解决方案分析

1. 若要打开**选项**对话框中，Visual Studio 中的菜单栏上选择**工具** > **选项**。

1. 在**选项**对话框框中，选择**文本编辑器** > **C#**或**基本** >  **高级**。

1. 选择**启用完整解决方案分析**复选框以启用完整解决方案分析，或清除相应的框以禁用它。 选择**确定**按钮完成后。

    ![启用完整解决方案分析复选框。] (../code-quality/media/fsa_toolsoptions.png "FSA_ToolsOptions")

## <a name="results-of-enabling-and-disabling-full-solution-analysis"></a>启用和禁用完整解决方案分析结果

在以下屏幕截图中，你可以启用完整解决方案分析后看到结果。 所有错误和中的代码分析问题*所有*的解决方案中的文件出现，无论这些文件是否是打开。

![启用完整解决方案分析。] (../code-quality/media/fsa_enabled.png "FSA_Enabled")

下面的屏幕截图显示禁用完整解决方案分析后的同一解决方案中的结果。 仅错误和代码分析问题，在错误列表中打开的解决方案文件会出现。

![禁用的完整解决方案分析。] (../code-quality/media/fsa_disabled.png "FSA_Disabled")

## <a name="automatically-disabling-full-solution-analysis"></a>自动禁用完整解决方案分析

如果 Visual Studio 检测到 200 MB 或更少的系统内存可供它，它会自动禁用完整解决方案分析 （以及某些其他功能） 如果启用它。 如果发生这种情况，则会出现警报，通知你这些。 一个按钮，可以根据需要重新启用完整解决方案分析。

![警报文本中挂起完整解决方案分析](../code-quality/media/fsa_alert.png "FSA_Alert")