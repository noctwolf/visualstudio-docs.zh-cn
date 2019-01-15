---
title: “常规”&gt;“调试”&gt;“选项”对话框 | Microsoft Docs
ms.date: 11/09/2018
ms.topic: reference
f1_keywords:
- vs.debug.options.General
- VS.ToolsOptionsPages.Debugger.General
- VS.ToolsOptionsPages.Debugger.ENC
- vs.debug.options.ENC
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Options dialog box, debugging
ms.assetid: b33aee0b-43c3-4c26-8ed4-bc673f491503
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9fa48ff41739752ff37817192b26483a23579419
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53829468"
---
# <a name="general-debugging-options"></a>常规调试选项

若要设置 Visual Studio 调试器选项，请选择**工具** > **选项**，然后在**调试**选择或取消选择框旁边**常规**选项。 可以还原所有默认设置**工具** > **导入和导出设置** > **重置所有设置**。 若要重置设置的子集，请保存你的设置与**导入和导出设置向导**在你想要测试更改之前，然后导入你已保存的设置之后。

您可以设置以下**常规**选项：

**在删除所有断点之前询问**：  
在完成“删除所有断点”命令前需要进行确认。

**一个进程中断时则中断所有进程**：  
发生一个中断时，同时中断调试器连接到的所有进程。

**当异常跨越 AppDomain 或托管/本机边界时中断**：  
在托管或混合模式调试中，如果满足以下条件，公共语言运行时可能会捕获跨越应用程序域边界或托管/本机边界的异常：

1. 当本机代码使用 COM 互操作调用托管代码而托管代码却引发异常时。 请参阅[COM 互操作介绍](/dotnet/articles/visual-basic/programming-guide/com-interop/introduction-to-com-interop)。

2. 当在应用程序域 1 中运行的托管代码调用应用程序域 2 中的托管代码，而应用程序域 2 中的代码却引发异常时。 请参阅[使用应用程序域编程](/dotnet/articles/framework/app-domains/index)。

3. 当代码调用一个函数通过使用反射，而该函数将引发异常。 请参阅[反射](/dotnet/framework/reflection-and-codedom/reflection)。

在 2 和 3 的情况，异常有时由捕获中的托管代码`mscorlib`而不是公共语言运行时。 此选项不影响在 `mscorlib` 捕获到异常时中断。

**启用地址级调试**：  
启用在地址级上进行调试的高级功能（“反汇编”窗口、“寄存器”窗口和地址断点）。

- **如果源不可用，则显示反汇编**：  
    会自动显示**反汇编**窗口时调试的代码的源是为其不可用。

**启用断点筛选器**：  
允许你在断点上设置筛选器，使其仅影响特定的进程、线程或计算机。

**使用新的异常帮助器**：  
使替换异常助手异常帮助器 (Visual Studio 2017)。

> [!NOTE]
> 对于托管代码，此选项之前已调用**启用异常助手**。

**启用“仅我的代码”**：  
调试器仅显示和单步执行用户代码（“我的代码”），而忽略系统代码和其他经过优化或没有调试符号的代码。

- **启动时若没有用户代码则发出警告(仅限托管)**：  
    如果在调试时启用“仅我的代码”，此选项会在没有用户代码（“我的代码”）的情况下发出警告。

**启用 .NET Framework 源代码单步执行**：  
允许调试器单步执行 .NET Framework 源代码。 自动启用此选项会禁用仅我的代码。 .NET framework 符号将下载到缓存位置。 更改缓存位置与**选项**对话框中，**调试**类别中，**符号**页。

**单步执行属性和运算符(仅限托管)**：  
防止调试器单步执行托管代码中的属性和运算符。

**启用属性求值和其他隐式函数调用**：  
在变量窗口和“快速监视”对话框中打开属性的自动求值和隐式函数调用。

- **在变量窗口中对对象调用字符串转换函数(仅限 C# 和 JavaScript)**：  
    在变量窗口中计算对象时，执行隐式字符串转换调用。 结果显示为字符串而不是类型名称。 仅在 C# 代码中进行调试时适用。 此设置可能由 DebuggerDisplay 特性重写 (请参阅[使用 DebuggerDisplay 特性](../debugger/using-the-debuggerdisplay-attribute.md))。

**启用源服务器支持**：  
指示 Visual Studio 调试器从实现 SrcSrv (`srcsrv.dll`) 协议的源服务器中获取源文件。 Team Foundation Server 和 Windows 的调试工具是实现协议的两个源服务器。 有关 SrcSrv 设置的详细信息，请参阅[SrcSrv](/windows-hardware/drivers/debugger/srcsrv)文档。 此外，请参阅[指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)。

> [!IMPORTANT]
> 由于读取 .pdb 文件会执行文件中的任意代码，因此请确保信任此服务器。

- **将源服务器诊断消息打印到输出窗口**：  
    如果启用源服务器支持，此设置会打开诊断显示。

- **允许源服务器中的部分信任程序集(仅限托管)**：  
    若源服务器支持已启用，此设置将替代不检索部分信任程序集的源这一默认行为。

- **始终运行不受信任的源服务器命令并且不再提示**：  
    若源服务器支持已启用，此设置将替代运行不受信任的命令时进行提示这一默认行为。

**启用源链接支持**：  
    告知 Visual Studio 调试器下载源文件 *.pdb*文件包含源链接信息。 源链接的详细信息，请参阅[源链接规范](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/source_link.md)。

> [!IMPORTANT]
>  由于源链接将下载文件使用 http 或 https，因此请确保您信任 *.pdb*文件。

- **对于所有源链接请求，回退到 Git 凭据管理器身份验证**：  
    若源链接支持已启用且源链接请求未通过身份验证，则 Visual Studio 调用 Git 凭据管理器。

**突出显示断点和当前语句所在的整个行（仅限 C++）**：  
调试器突出显示断点或当前语句时，会突出显示整个行。

**要求源文件与原始版本完全匹配**：  
指示调试器验证源文件是否与用于构建待调试的可执行文件的源代码版本匹配。 若版本不匹配，系统会提示你查找匹配的源。 若找不到匹配的源，调试过程中将不会显示源代码。

**将所有输出窗口文本重定向到即时窗口**：  
将通常显示在“输出”窗口中的所有调试器消息改为发送到“即时”窗口。

**在变量窗口中显示对象的原始结构**：  
禁用所有对象的结构视图自定义。 有关视图自定义的详细信息，请参阅[创建 .managed 对象的自定义视图](../debugger/create-custom-views-of-dot-managed-objects.md)。

**在模块加载时取消 JIT 优化(仅限托管)**：  
在附加调试器的情况下，加载模块并编译 JIT 后，禁用托管代码的 JIT 优化。 禁用优化可能更易于调试某些问题，尽管这会降低性能。 如果正在使用“仅我的代码”，则取消 JIT 优化会导致非用户代码显示为用户代码（“我的代码”）。 有关详细信息，请参阅[JIT 优化和调试](../debugger/jit-optimization-and-debugging.md)。

**对 ASP.NET 启用 JavaScript 调试(Chrome、Edge 和 IE)**：  
启用脚本调试程序对 ASP.NET 应用程序。 在 Chrome 中的第一次使用，可能需要登录到浏览器来启用已安装的 Chrome 扩展。 禁用此选项可还原为旧行为。

**启用适用于 UWP JavaScript 应用的 Edge 开发人员工具(实验版)**：  
启用适用于 UWP JavaScript 应用在 Edge 中开发人员工具。

**对 ASP.NET 启用旧版 Chrome JavaScript 调试器**：  
启用旧版 Chrome JavaScript 脚本调试器对 ASP.NET 应用程序。 在 Chrome 中的第一次使用，可能需要登录到浏览器来启用已安装的 Chrome 扩展。

**在以管理员身份运行 Visual Studio 时使用试验性方法启动 Chrome JavaScript 调试**：  
告知 Visual Studio 尝试在 JavaScript 调试期间启动 Chrome 的新方法。

**加载 dll 导出(限本机)**：  
加载 DLL 导出表。 处理 Windows 消息、Windows 过程 (WindowProc)、COM 对象、封送或不具有其符号的任何 DLL 时，DLL 导出表中的符号信息将很有用。 读取 DLL 导出信息会占用一些系统开销。 因此，默认情况下此功能被禁用。

若要查看 DLL 导出表中的可用符号，请使用 `dumpbin /exports`。 符号可用于任何 32 位系统 DLL。 从 `dumpbin /exports` 输出中，可以查看到精确的函数名，包括非字母数字字符。 这对于在函数上设置断点很有用。 DLL 导出表中的函数名在调试器的其他位置似乎被截断了。 调用将按调用顺序列出，当前函数（嵌套最深的函数）位于顶端。 有关详细信息，请参阅 [dumpbin /exports](/cpp/build/reference/dash-exports)。

**自下而上显示并行堆栈关系图**：  
控制“并行堆栈”窗口中堆栈的显示方向。

**如果写入的数据未更改值，则忽略 GPU 内存访问异常**：  
如果数据未改变，则忽略在调试期间检测的争用条件。 有关详细信息，请参阅[调试 GPU 代码](../debugger/debugging-gpu-code.md)。

**使用托管兼容模式**：  
将默认调试引擎替换为旧版本，以支持以下方案：

- 使用.NET Framework 语言不C#，Visual Basic 或F#，它提供其自己的表达式计算器 (包括 C + + CLI)。

- 你想要在混合的模式调试过程中 c + + 项目启用编辑并继续。

> [!NOTE]
> 选择托管兼容模式会禁用仅在默认调试引擎中实现某些功能。 在 Visual Studio 2012 中取代旧调试引擎。

**使用旧版 C# 和 VB 表达式计算器**：  
调试器将使用 Visual Studio 2013C#或 Visual Basic 表达式计算器而不是基于 Visual Studio 2015 Roslyn 的表达式计算器。

**当使用自定义调试器可视化工具时对潜在的不安全进程(仅限托管)发出警告**：  
当使用在调试对象进程中运行代码的自定义调试器可视化工具时，Visual Studio 会发出警告，因为它可能在运行不安全代码。

**启用 Windows 调试堆分配器(仅限本地)**：  
启用 Windows 调试堆以改进堆诊断。 启用此选项会影响调试性能。

**启用 XAML 的 UI 调试工具**：  
在开始调试 (F5) 支持的项目类型时，将显示“实时可视化树”和“实时属性资源管理器”窗口。 有关详细信息，请参阅[调试时检查 XAML 属性](../debugger/inspect-xaml-properties-while-debugging.md)。

- **预览实时可视化树中的所选元素**：  
    选定了其上下文的 XAML 元素在“实时可视化树”窗口中也会被选中。

- **在应用程序中显示运行时工具**：  
    演示**实时可视化树**在正在调试的 XAML 应用程序的主窗口工具栏中的命令。 Visual Studio 2015 Update 2 中引入了此选项。

- **启用“XAML 编辑并继续”**：  
    可以使用编辑并继续使用 XAML 代码的功能。

**调试时启用诊断工具**：  
在进行调试时，将显示“诊断工具”窗口。

**在调试过程中显示运行时间 PerfTip**：  
在进行调试时，代码窗口会显示给定方法调用的运行时间。

**启用“编辑并继续”**：  
调试时启用编辑并继续功能。

- **启用本机“编辑并继续”**：  
    在调试本机 C++ 代码时，你可以使用“编辑并继续”功能。 有关详细信息，请参阅[编辑并继续 （Visual c + +）](../debugger/edit-and-continue-visual-cpp.md)。

- **继续应用更改（仅限本机）**：  
    在从中断状态继续该过程时，Visual Studio 会自动编译并应用你所做的任何未完成的代码更改。 如果未选中，可以选择使用“调试”菜单下的“应用代码更改”项来应用更改。

- **警告过时代码（仅限本机）**：  
    收到关于陈旧代码的警告。

**显示运行到单击按钮在编辑器中进行调试时**:  
选中此选项后，[运行时单击](debugger-feature-tour.md#run-to-a-point-in-your-code-quickly-using-the-mouse)调试时，将会显示按钮。

**调试停止时自动关闭控制台**：  
会告知 Visual Studio 调试会话结束时关闭控制台。

## <a name="options-available-in-older-versions-of-visual-studio"></a>较旧版本的 Visual Studio 中的可用选项

如果你使用 Visual Studio 的较旧版本，可能会出现一些其他选项。

**启用异常助手**：  
对于托管代码，使异常助手。 在 Visual Studio 2017 中，异常帮助器替换为异常助手。

**在未经处理的异常上展开调用堆栈**：  
导致“调用堆栈”窗口将调用堆栈回滚到未经处理的异常发生之前的时间点。

**启动时若无符号则发出警告(仅限本机)**：  
调试的程序调试程序对其具有没有对应符号信息时显示一个警告对话框。

**如果启动时禁用了脚本调试，发出警告**：  
如果在启动调试器时禁用了脚本调试，则会显示警告对话框。

**使用本机兼容性模式**：  
选中此选项后，调试器使用 Visual Studio 2010 本机调试器而不是新的本机调试器。

- 如果正在调试.NET c + + 代码，因为新的调试引擎不支持计算.NET c + + 表达式，就使用此选项。 但是，启用本机兼容模式会禁用依赖于当前调试器实现来操作的许多功能。 例如，旧引擎缺少很多可视化工具内置类型，例如`std::string`Visual Studio 2015 项目中。   使用 Visual Studio 2013 项目以在这些情况下获得最佳的调试体验。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中进行调试](../debugger/index.md)
- [调试器功能简介](../debugger/debugger-feature-tour.md)