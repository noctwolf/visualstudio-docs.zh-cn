---
title: "优化 Visual Studio 性能 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- startup time [Visual Studio]
- optimizing performance [Visual Studio]
- speed up start time [Visual Studio]
ms.assetid: d1508121-8499-4084-8eb5-fa89fa7b17d3
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.performancecenter
ms.technology: vs-ide-general
ms.openlocfilehash: d1058ca5762db28f0afc678a9d31cc6f0f3be6bc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="optimize-visual-studio-performance"></a>优化 Visual Studio 性能
Visual Studio 可快速高效地启动。 但是，某些 Visual Studio 扩展和工具窗口加载时会对启动时间产生不利影响。 可以在“管理 Visual Studio 性能“对话框中控制缓慢扩展和工具窗口的行为。 有关提升性能的更多提示，请参阅 [Visual Studio 性能提示和技巧](../ide/visual-studio-performance-tips-and-tricks.md)。  

## <a name="startup-behavior"></a>启动行为

为了避免启动时间延长，Visual Studio 2017 使用按需方法加载扩展。 该行为意味着不会在 Visual Studio 启动后立即打开扩展，而是根据需要打开。 此外，由于在之前的 Visual Studio 会话中保持工具窗口的打开状态会使启动时间变慢，因此 Visual Studio 以更智能的方式打开工具窗口，从而避免影响启动时间。  

如果 Visual Studio 检测到启动速度较慢，则会弹出一条消息，提示你导致速度变慢的扩展或工具窗口。 此消息提供了指向“管理 Visual Studio 性能”对话框的链接。 还可以通过在菜单栏中选择“帮助”、“管理 Visual Studio 性能”，访问此对话框。  

![“管理 Visual Studio 性能”- 弹出窗口显示“我们注意到扩展 ... 正在拖慢 Visual Studio”](../ide/media/vside_perfdialog_popup.png)

该对话框会列出影响启动性能的扩展和工具窗口。 可更改扩展和工具窗口的设置以提高启动性能。  

## <a name="to-change-extension-settings-to-improve-startup-solution-load-and-typing-performance"></a>更改扩展设置以改善启动、解决方案加载和键入性能

1. 通过在菜单栏上选择“帮助”、“管理 Visual Studio 性能”，打开“管理 Visual Studio 性能”对话框。  

    如果某个扩展使 Visual Studio 的启动、解决方案加载或键入变慢，此扩展将显示在“扩展”、“启动”（或“解决方案加载”或“键入”）下的“管理 Visual Studio 性能”对话框中。  

    ![管理 Visual Studio 性能 - 扩展视图](../ide/media/vside_perfdialog_extensions.png)

2. 选择想要禁用的扩展，然后选择“禁用”按钮。  

可以始终使用“扩展管理器”或“管理 Visual Studio 性能”对话框重新启用扩展，以用于以后的会话。

## <a name="to-change-tool-window-settings-to-improve-startup-time"></a>更改工具窗口设置以改善启动时间

1. 通过在菜单栏上选择“帮助”、“管理 Visual Studio 性能”，打开“管理 Visual Studio 性能”对话框。  

    如果某个工具窗口使 Visual Studio 启动变慢，此工具窗口将显示在“工具窗口”、“启动”下的“管理 Visual Studio 性能”对话框中。  

2. 选择想要更改其行为的工具窗口。  

3. 选择下列三个选项的其中一个：    

    - “使用默认行为”：工具窗口的默认行为。 选中此项将不会提升启动性能。  

    - “启动时不显示窗口”：打开 Visual Studio 时，指定的工具窗口将始终关闭，即使它在上一个会话中保留打开状态。 需要时可以从相应的菜单中打开工具窗口。  
    
    - **启动时自动隐藏窗口：**如果工具窗口在上一个会话中保留打开状态，则此选项将在启动时折叠工具窗口组，以避免初始化工具窗口。 如果经常使用工具窗口，那么这是一个不错的选择。 因为工具窗口仍然可用，但不会再对 Visual Studio 启动时间产生负面影响。  

    ![管理 Visual Studio 性能 - 工具窗口视图](../ide/media/vside_perfdialog_toolwindows.png)

## <a name="speed_up_solution_load"></a>在 Visual Studio 2017 中更快加载大型解决方案

Visual Studio 2017 引入了新功能“轻型解决方案加载”，可减少在 IDE 中加载大型解决方案所需的时间和内存。 如果你有包含多个 C#、VB 或 C++ 项目的大型解决方案，则启用轻型解决方案加载可能会看到显著的性能优势。 若要详细了解如何使用此功能从中受益，请参阅[优化解决方案加载](../ide/optimize-solution-loading-in-visual-studio.md)。

### <a name="enable-or-disable-lightweight-solution-load"></a>启用或禁用轻型解决方案加载

可以右键单击“解决方案资源管理器”中的解决方案名称，并选择“启用轻型解决方案加载”。 选择此选项后，需要关闭并重新打开解决方案，才能激活轻型解决方案加载。

![“解决方案资源管理器”](../ide/media/VSIDE_LSL_Solution_Setting.png)

若要配置轻型解决方案加载的全局设置，请参阅[优化解决方案加载](../ide/optimize-solution-loading-in-visual-studio.md#global_solution_load_settings)。

## <a name="see-also"></a>另请参阅
[Visual Studio 性能提示和技巧](../ide/visual-studio-performance-tips-and-tricks.md)
