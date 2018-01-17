---
title: "Visual Studio 中的调试入门 | Microsoft Docs"
ms.custom: 
ms.date: 12/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3a14d28-d811-4ff3-bd09-21dce14025ca
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c75b5508cd23a2131bcdd64cf52aacc1486d2713
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="get-started-with-debugging-in-visual-studio"></a>Visual Studio 中的调试入门
Visual Studio 提供一组强大的集成项目生成和调试工具。 本主题将介绍如何开始使用一组最基本的调试 UI 功能。  

## <a name="my-code-doesnt-work-help-me-visual-studio"></a>我的代码不起作用。 请帮助我，Visual Studio！  
 你已经想到了编辑器并创建了一些代码。 现在，你想要开始调试该代码。 与大多数 IDE 一样，Visual Studio 有两个调试阶段：生成代码以捕获并解决项目和编译器错误；在环境中运行代码以捕获并解决运行时和动态错误。  

### <a name="build-your-code"></a>生成代码  
 生成配置有两种基本类型：**调试**和**发布**。 第一种配置生成更慢、更大的可执行文件，此可执行程序实现更丰富的交互式运行时调试体验，但应永远不会投入市场销售。 第二种配置生成更快、更优化的可执行文件，此可执行文件适合投入市场销售（至少从编译器的角度来看是这样）。 默认的生成配置是**调试**。

生成项目最简单的方法是按 F7，但是还可以在主菜单中选择“生成”>“生成解决方案”开始生成项目。  

 ![Visual Studio 生成项目菜单选择](../ide/media/vs_ide_gs_debug_build_menu_item.png "Vs_ide_gs_debug_build_menu_item")  

 可以在 Visual Studio UI 底部的“输出”状态窗口中观察生成过程。 该窗口将显示错误、警告和生成操作。 如果出现错误（或者在配置的级别出现警告），你的生成将失败。 你可以单击错误和警告以转到出现错误和警告的行。 通过再次按 **F7**（仅重新编译出现错误的文件）或按 **Ctrl+Alt+F7**（适用于全新且完整的重新生成）重新生成项目。  

 编辑器下方的结果窗口中有两个生成选项卡式窗口：**输出**窗口（它包含原始编译器输出，包括错误消息）和**错误列表**窗口（它提供所有错误和警告的可排序和可筛选列表）。  

 如果操作成功，可在**输出**窗口中看到类似以下结果。  

 ![Visual Studio 成功的生成输出](../ide/media/vs_ide_gs_debug_success_build.PNG "vs_ide_gs_debug_success_build")  

### <a name="review-the-error-list"></a>审阅错误列表  
 除非未对之前成功编译的代码进行修改，否则很可能出现错误。 如果不熟悉编码，则可能出现许多错误。 错误有时很明显，如简单的语法错误或不正确的变量名，有时它们则难以理解，只有一个神秘代码显示给你。 有关这些问题更清晰的视图，请导航至生成“输出”窗口的底部，然后单击“错误列表”选项卡。在此选项卡中，你可以看到关于项目错误和警告的一个更有条理的视图，并为你提供一些额外的选项。  

 ![Visual Studio 输出和错误列表](../ide/media/vs_ide_gs_debug_bad_build_error_list.PNG "Vs_ide_gs_debug_bad_build_error_list")  

 单击“错误列表”窗口中的错误行，并跳转至发生错误的行。 （或单击右上方的“快速启动”栏，在其中键入行号，然后按 Enter，以打开行号。 这是转至“选项”窗口条目最快的方法，你可以在这里打开行号。 了解如何使用“快速启动”栏，可以省去多次单击 UI！）  

 ![具有行号的 Visual Studio 编辑器](../ide/media/vs_ide_gs_debug_line_numbers.png "Vs_ide_gs_debug_line_numbers")  

 ![Visual Studio 行号选项](../ide/media/vs_ide_gs_debug_options_line_numbers.png "Vs_ide_gs_debug_options_line_numbers")  

 使用 Ctrl+G 快速跳转至发生错误的行号。  

 错误由红色的“波形曲线”下划线标识。 将鼠标悬停在下划线上以获取其他详细信息。 修复后下划线消失，尽管纠正过程中可能会引入新的错误。 （此过程被称为“回归”。）  

 ![Visual Studio 错误悬停](../ide/media/vs_ide_gs_debug_error_hover1.png "Vs_ide_gs_debug_error_hover1")  

 遍历错误列表，并解决代码中的所有错误。  

 ![Visual Studio 调试错误窗口](../ide/media/vs_ide_gs_debug_error_list.PNG "Vs_ide_gs_debug_error_list")  

### <a name="review-errors-in-detail"></a>审阅错误的详细信息  
 许多错误可能对你没有意义，这些错误被当做编译器中的术语。 在这些情况下，你将需要其他信息。 在“错误列表”窗口中，可以通过右键单击相应条目行并从上下文菜单中选择“显示错误帮助”，执行自动必应搜索以获取错误（或警告）的详细信息。  

 ![Visual Studio 错误列表的必应搜索](../ide/media/vs_ide_gs_debug_error_list_error_help.png "Vs_ide_gs_debug_error_list_error_help")  

 此操作可打开 Visual Studio 内的一个选项卡，该选项卡中包含错误代码和文本的必应搜索结果。 结果来自 Internet 上许多不同的源，并且不是全部有用。  

 你也可以单击“错误列表”的“代码”列中的超链接错误代码值。 这将启动该错误代码的 Bing 搜索。  

### <a name="use-light-bulbs-to-fix-or-refactor-code"></a>使用“灯泡”修复或重构代码  
 灯泡是 Visual Studio 的新增功能，使用此功能可重构代码内联。 灯泡是快速、高效修复常见问题的简单方法。 若要使用灯泡，请右键单击某个警告波形曲线（或在将鼠标悬停在波形曲线上时按 Ctrl+. ），然后选择“快速操作”。  

 ![Visual Studio 灯泡快速选项](../ide/media/vs_ide_gs_debug_light_bulb1.png "Vs_ide_gs_debug_light_bulb1")  

 你将看到可应用于代码行的可能修复或重构方法列表。  

 ![Visual Studio 灯泡预览](../ide/media/vs_ide_gs_debug_light_bulb_preview_changes.PNG "Vs_ide_gs_debug_light_bulb_preview_changes")  

 只要代码分析器确定有机会修复、重构或改进你的代码，就能使用灯泡。 单击任意代码行，右键单击以打开上下文菜单，然后选择“快速操作”（或者如果注重效率，请再次按 Ctrl+.）。 如果有可用的区域重构或改进选项，将显示这些选项；否则，IDE 的左下角面板将显示消息 `No quick options available here`。  

 ![Visual Studio 灯泡“无选项”文本](../ide/media/vs_ide_gs_debug_light_bulb_no_options.PNG "Vs_ide_gs_debug_light_bulb_no_options")  

 根据经验，可以快速使用箭头键和 Ctrl+. 检查“快速选项”重构机会并清理你的代码！  

 有关灯泡的详细信息，请阅读[使用灯泡执行快速操作](../ide/perform-quick-actions-with-light-bulbs.md)。  

### <a name="debug-your-running-code"></a>调试运行代码  
 现在已成功生成了代码并执行了一些清理，请按 F5 或者选择“调试”>“开始调试”来运行代码。 这将在调试环境中启动你的应用，便于你观察其详细行为。 Visual Studio IDE 在应用运行时会发生变化：“输出”窗口由两个新窗口代替（使用默认的窗口配置），这两个新窗口分别是“自动/局部变量/监视”选项卡式窗口和“调用堆栈/断点/异常设置/输出”选项卡式窗口。 这两个窗口具有多个选项卡，可用于检查和评估应用的变量、线程、调用堆栈及其运行时的各种其他行为。  

 ![Visual Studio 自动和调用堆栈窗口](../ide/media/vs_ide_gs_debug_autos_and_call_stack.PNG "Vs_ide_gs_debug_autos_and_call_stack")  

 按 Shift+F5 或单击“停止”按钮可以停止应用。 或者，可以仅关闭应用的主窗口（或命令行对话框）。  

 如果你的代码按预期完美而准确地运行，祝贺你！ 但是，如果它挂起、崩溃，或带来一些奇怪的结果，则需要找到这些问题的根源并修复 bug。  

### <a name="set-simple-breakpoints"></a>设置简单断点  
 断点是可靠调试的最基本和最重要的功能。 断点指示 Visual Studio 应在哪个位置挂起你的运行代码，以使你可以查看变量的值或内存的行为，或确定代码的分支是否运行。 在设置或移除断点后，你不需要重新生成项目。  

 通过单击想要发生中断的行的远端边距来设置一个断点，或按 F9 在当前代码行上设置断点。 运行代码时，它将在执行此代码行的指令之前暂停（或中断）。  

 ![Visual Studio 断点](../ide/media/vs_ide_gs_debug_breakpoint1.png "Vs_ide_gs_debug_breakpoint1")   

 断点的常见用途包括：  

1.  缩小崩溃或挂起的根源，将它们分散在你认为引起失败的方法调用的代码中。 在调试器中运行代码时，请移除断点，然后重设断点使其更紧密，直到找到有问题的代码行。  请参阅下一部分，了解如何在调试器中运行代码。

2.  引入新代码时，请在代码的开头设置断点并运行代码，确保它按预期方式运行。

3.  如果已实现复杂的行为，请为算法代码设置断点，以便在程序中断时检查变量和数据的值。  

4.  如果正在编写 C 或 C++ 代码，请使用断点停止该代码，以便在调试内存相关故障时检查地址值（查找 NULL）和引用计数。  

 有关使用断点的详细信息，请阅读[使用断点](../debugger/using-breakpoints.md)。  

### <a name="inspect-your-code-at-run-time"></a>在运行时检查代码  
 运行的代码命中断点并暂停时，标记为黄色的代码行（当前语句）尚未执行。 此时，建议执行当前语句，然后检查更改的值。 可以使用多个 step 命令在调试器中执行代码。 如果标记的代码是方法调用，可以按 F11 单步执行它。 还可以按 F10，“逐过程”执行该代码行。 有关其他命令及如何逐步执行代码的详细信息，请阅读[使用调试器浏览代码](../debugger/navigating-through-code-with-the-debugger.md)。

 ![Visual Studio 运行时值检查](../ide/media/vs_ide_gs_debug_hit_breakpoint.PNG "vs_ide_gs_debug_inspect_value") 

 在上图中，可以按 F10 或 F11 使调试器前移一条语句（由于此处没有方法调用，因此这两个命令的结果相同）。

 调试器暂停时，可以检查变量并调用堆栈来确定所出现的情况。 这些值是否在你期望的范围内？ 调用是否正按正确的顺序进行？  

 ![Visual Studio 运行时值检查](../ide/media/vs_ide_gs_debug_inspect_value.PNG "vs_ide_gs_debug_inspect_value")  

 将鼠标悬停在变量上以查看它当前包含的值和引用。 如果出现意外值，则表示代码的前一行或调用行可能出现了 bug。  有关更深入的信息，请[了解更多](../debugger/getting-started-with-the-debugger.md)使用调试器的信息。 

 此外，Visual Studio 显示“诊断工具”窗口，可从其中观察随时间变化的应用的 CPU 和内存使用情况。 之后在开发应用时，可以使用这些工具查找意外的高 CPU 使用率或内存分配。 结合使用“监视”窗口和断点，确定导致意外的高使用率或未释放的资源的原因。  有关详细信息，请参阅[分析功能简介](../profiling/profiling-feature-tour.md)。

### <a name="run-unit-tests"></a>运行单元测试  
 单元测试是代码 bug 的第一个防线，因为正确完成单元测试后，它们会测试一个“单元”的代码（一般是单个函数），并且通常调试起来比调试完整程序更简单。 Visual Studio 安装了适用于托管和本机代码的 Microsoft 单元测试框架。 使用单元测试框架创建单元测试，运行测试，然后报告这些测试的结果。 进行更改后重新运行单元测试，以测试代码仍能正常工作。 使用 Visual Studio Enterprise 时，可以在每次生成后自动运行测试。  

 请阅读[使用 IntelliTest 为代码生成单元测试](../test/generate-unit-tests-for-your-code-with-intellitest.md)获取入门指南。  

 若要了解有关 Visual Studio 中的单元测试以及它们如何帮助你创建更高质量代码的详细信息，请阅读[单元测试的基础知识](../test/unit-test-basics.md)。  

### <a name="perform-static-code-analysis"></a>执行静态代码分析  
 “静态代码分析”是“自动检查我的代码是否存在可能导致运行时错误或代码管理问题的常见问题”的流行说法。 养成在清除了阻止生成的明显错误后运行该分析的习惯，然后花一些时间解决其可能产生的警告。 你将为自己省去一些将来的麻烦，并了解几种代码样式技术。  

 按 Alt+F11（或从顶部菜单选择“分析”>“对解决方案运行代码分析”）启动静态代码分析。 如果你有大量代码，这可能需要一些时间。  

 ![Visual Studio 代码分析菜单项](../ide/media/vs_ide_gs_debug_run_code_analysis.png "Vs_ide_gs_debug_run_code_analysis")  

 任何新的或更新的警告都将显示在 IDE 底部的“错误列表”选项卡中。 单击警告以跳转到相应的行。  

 ![带警告的 Visual Studio 错误列表](../ide/media/vs_ide_gs_debug_code_analysis_warning_error_list.PNG "vs_ide_gs_debug_code_analysis_warning_error_list")  

 警告将用明亮的黄绿色（而非红色）波形曲线标识。 将鼠标悬停在波形曲线上方以获取详细信息，右键单击波形曲线获取获取上下文菜单以帮助修复或重构选项。  

 ![Visual Studio 代码分析警告悬停](../ide/media/vs_ide_gs_debug_code_analysis_warning_hover.png "vs_ide_gs_debug_code_analysis_warning_hover")  

## <a name="see-also"></a>请参阅  
 [调试器功能简介](../debugger/debugger-feature-tour.md)  
 [了解更多使用调试器的信息](../debugger/getting-started-with-the-debugger.md)
