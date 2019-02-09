---
title: 启用或禁用代码分析
ms.date: 10/25/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 4878c25021d87e91f6a575d11a876d7aac2455d5
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55918125"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>如何：启用和禁用托管代码的自动代码分析

可以配置 （静态） 的代码分析，以托管的代码项目中的每个生成后运行。 可以设置不同的代码分析每个生成配置属性，例如，调试和发布。

本文适用仅为静态代码分析并不实时代码分析，并使用[Roslyn 代码分析器](roslyn-analyzers-overview.md)。

## <a name="to-enable-or-disable-automatic-code-analysis"></a>若要启用或禁用自动代码分析

1. 在中**解决方案资源管理器**，右键单击该项目，然后选择**属性**。

1. 在项目属性对话框中，选择**代码分析**选项卡。

   > [!TIP]
   > 较新的项目类型，如.NET Core 和.NET Standard 的应用程序无**代码分析**选项卡。静态代码分析不适用于这些项目类型，但您仍可以获得实时代码分析，并使用[Roslyn 代码分析器](roslyn-analyzers-overview.md)。 若要禁止显示 Roslyn 代码分析器的警告，请参阅本文末尾处的注释。

1. 指定在生成类型**配置**和中的目标平台**平台**。

1. 若要启用或禁用自动代码分析，请选择或清除**生成时启用代码分析**复选框。

> [!NOTE]
> **生成时启用代码分析**复选框仅影响静态代码分析。 它不会影响[Roslyn 代码分析器](roslyn-analyzers-overview.md)，它始终执行在生成，如果安装作为 NuGet 包。 如果你想要清除从分析器错误**错误列表**，可以通过选择禁止显示所有当前的冲突**分析** > **运行代码分析并取消处于活动状态问题**菜单栏上。 有关详细信息，请参阅[禁止显示冲突](use-roslyn-analyzers.md#suppress-violations)。
