---
title: 如何：启用和禁用托管代码的自动代码分析
ms.date: 09/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 3113143b07ccb6f765cd0cf1735b34be6e952c72
ms.sourcegitcommit: 6672a1e9d135d7e5cca3cceea07c6fe5a0871475
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2018
ms.locfileid: "47443540"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>如何： 启用和禁用托管代码的自动代码分析

可以配置代码分析，以托管的代码项目中的每个生成后运行。 可以设置不同的代码分析每个生成配置属性，例如，调试和发布。

## <a name="to-enable-or-disable-automatic-code-analysis"></a>若要启用或禁用自动代码分析

1. 在中**解决方案资源管理器**，右键单击该项目，然后选择**属性**。

1. 在项目属性对话框中，选择**代码分析**选项卡。

1. 指定在生成类型**配置**和中的目标平台**平台**。

1. 若要启用或禁用自动代码分析，请选择或清除**生成时启用代码分析**复选框。

> [!NOTE]
> **生成时启用代码分析**复选框仅影响静态代码分析。 它不会影响[Roslyn 代码分析器](roslyn-analyzers-overview.md)，它始终执行在生成，如果安装作为 NuGet 包。 如果你想要清除从分析器错误**错误列表**，可以通过选择禁止显示所有当前的冲突**分析** > **运行代码分析并取消处于活动状态问题**菜单栏上。 有关详细信息，请参阅[禁止显示冲突](use-roslyn-analyzers.md#suppress-violations)。
