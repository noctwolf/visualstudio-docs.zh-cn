---
title: 如何： 启用和禁用托管代码的完整解决方案分析
ms.date: 03/23/2018
ms.topic: conceptual
helpviewer_keywords:
- full solution analysis
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.workload:
- dotnet
ms.openlocfilehash: d227360be39455662d3d2ebe822810debd655dac
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31922767"
---
# <a name="how-to-enable-and-disable-full-solution-analysis-for-managed-code"></a>如何： 启用和禁用托管代码的完整解决方案分析

*完整解决方案分析*是关闭的 Visual Studio 功能，使你可以查看仅在你的解决方案中打开的 Visual C# 或 Visual Basic 文件中的代码分析问题或还在代码中的文件。 默认情况下，完整解决方案分析是*启用*适用于 Visual Basic 和*禁用*对于 Visual C#。

它在某些情况下可能很有用，若要查看所有文件中的所有问题，但它还可让人分散注意力。 如果你的解决方案是非常大，或包含许多文件，它会向下降低 Visual Studio。 若要限制显示的问题数和改进 Visual Studio 性能，你可以禁用完整解决方案分析。 如有必要，您便可以轻松地重新启用此功能。

## <a name="to-toggle-full-solution-analysis"></a>若要切换完整解决方案分析

1. 若要打开**选项**对话框中，Visual Studio 中的菜单栏上选择**工具** > **选项**。

1. 在**选项**对话框框中，选择**文本编辑器** > **C#** 或**基本** >  **高级**。

1. 选择**启用完整解决方案分析**复选框以启用完整解决方案分析，或清除相应的框以禁用它。 选择**确定**当你已完成。

    ![启用完整解决方案分析复选框。](../code-quality/media/options-enable-full-solution-analysis.png)

## <a name="results-of-enabling-and-disabling-full-solution-analysis"></a>启用和禁用完整解决方案分析结果

在以下屏幕截图中，你可以启用完整解决方案分析后看到结果。 所有错误和中的代码分析问题*所有*的解决方案中的文件出现，无论这些文件是否是打开。

![启用完整解决方案分析。](../code-quality/media/fsa_enabled.png)

下面的屏幕截图显示禁用完整解决方案分析后的同一解决方案中的结果。 只有错误和打开的解决方案文件中的代码分析问题出现在**错误列表**。

![禁用的完整解决方案分析。](../code-quality/media/fsa_disabled.png)

## <a name="automatically-disable-full-solution-analysis"></a>自动禁用完整解决方案分析

如果 Visual Studio 检测到 200 MB 或更少的系统内存可供它，它会自动禁用完整解决方案分析 （和某些其他功能） 如果启用它。 如果发生这种情况，则会出现警报，通知你 Visual Studio 已禁用某些功能。 按钮可以重新启用完整解决方案分析，如果你想。

![警报文本中挂起完整解决方案分析](../code-quality/media/fsa_alert.png)