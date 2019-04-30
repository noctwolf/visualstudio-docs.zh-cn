---
title: Visual Studio 扩展程序的每个监视器感知功能支持
titleSuffix: ''
description: 了解有关每个监视器-识别功能在 Visual Studio 2019 中可用的新扩展器支持。
ms.date: 04/10/2019
helpviewer_keywords:
- Visual Studio, PMA, per-monitor-awareness, extenders, Windows Forms
- Per-Monitor Awareness support for extenders
ms.assetid: ''
author: rub8n
ms.author: rurios
manager: anthc
ms.prod: visual-studio-windows
monikerRange: vs-2019
ms.technology: vs-ide-general
ms.topic: reference
ms.workload:
- multiple
ms.openlocfilehash: 44938c5753491521702867398a514f770cf831fb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62793629"
---
# <a name="per-monitor-awareness-support-for-visual-studio-extenders"></a>Visual Studio 扩展程序的每个监视器感知功能支持
Visual Studio 2019 之前的版本必须设置为系统识别，而不是按监视器 DPI 感知 (PMA) 其 DPI 感知上下文。 运行中系统识别导致降级视觉对象体验 （例如模糊字体或图标），只要 Visual Studio 必须呈现跨具有不同的缩放比例或远程监视器到具有不同的显示配置的计算机例如 （不同Windows 扩展的)。

Visual Studio 2019 DPI 感知上下文设置为 PMA，当环境支持此功能，允许 Visual Studio 来呈现根据托管它的位置显示的配置而不是单个系统定义的配置。 最终将转换为支持 PMA 模式的表面区域始终清晰 UI。

请参阅[在 Windows 上的高 DPI 桌面应用程序开发](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)本文档中介绍的有关条款和总体方案的详细信息文档。

## <a name="quickstart"></a>快速入门
- 确保在 PMA 模式下运行 Visual Studio (请参阅**启用 PMA**)

- 常见方案的一组正确验证扩展插件的工作原理 (请参阅**测试你的扩展 PMA 问题**)

- 如果你发现的问题，可以使用本文档中讨论的策略/建议来诊断并解决这些问题。 您还需要添加新[Microsoft.VisualStudio.DpiAwareness](https://www.nuget.org/packages/Microsoft.VisualStudio.DpiAwareness/)到你的项目以访问所需的 Api 的 NuGet 包。

## <a name="enabling-pma"></a>启用 PMA
若要启用 PMA Visual Studio 中的，需要满足以下要求：
1) Windows 10 2018 年 4 月更新 (v1803，RS4) 或更高版本
2) .NET framework 4.8 RTM 或更高版本
3) 使用 visual Studio 2019 ["具有不同像素密度屏幕的优化呈现"](https://docs.microsoft.com/visualstudio/ide/reference/general-environment-options-dialog-box?view=vs-2019)选项处于启用状态

一旦满足这些要求，则 Visual Studio 将自动启用 PMA 模式整个过程。

> [!NOTE]
> 仅当具有 Visual Studio 2019 Update #1 时，VS （例如属性浏览器） 中的 Windows 窗体内容将支持 PMA。

## <a name="testing-your-extensions-for-pma-issues"></a>测试你的扩展 PMA 问题

Visual Studio 正式支持 WPF、 Windows 窗体、 Win32、 和 HTML/JS UI 框架。 当 Visual Studio 将进入 PMA 模式时，每个 UI 堆栈的行为有所不同。 因此，无论 UI 框架，建议执行测试流程是为了确保所有 UI 符合 PMA 模式。

建议验证以下常见方案：

1. 更改单个监视器环境的缩放比例，该应用程序时运行 *
    - 此方案可帮助测试 UI 响应动态的 Windows 在 DPI 更改

2. 停靠/移除便携式计算机在其中附加的监视器设置为主要和附加的监视器具有不同的缩放因子比在便携式计算机，运行该应用程序时。
    - 此方案可帮助测试 UI 正在显示响应，添加或移除在 DPI 更改，以及处理动态显示

3. 具有不同的缩放比例的多个监视器和它们之间移动应用程序。
    - 此方案可帮助测试 UI 响应显示 DPI 更改
    
4. 到在本地和远程计算机的主监视器所需不同的缩放比例的计算机的远程处理。
    - 此方案可帮助测试 UI 响应动态的 Windows 在 DPI 更改

你的 UI 是否可能会遇到问题的好初步测试是代码的利用是否*Microsoft.VisualStudio.Utilities.Dpi.DpiHelper*， *Microsoft.VisualStudio.PlatformUI.DpiHelper*，或*VsUI::CDpiHelper*类。 这些旧 DpiHelper 类仅支持系统 DPI 感知，PMA 过程时不会始终正常工作。

这些 DpiHelpers 的典型用法如下：

```cs
Point screenTopRight = logicalBounds.TopRight.LogicalToDeviceUnits();

POINT screenIntTopRight = new POINT
{
    x = (int)screenTopRIght.X,
    y = (int)screenTopRIght.Y
}

// Declared via P/Invoke
IntPtr monitor = MonitorFromPoint(screenIntTopRight, MONITOR_DEFAULTTONEARST);
```

在上一示例中，表示一个窗口的逻辑边界矩形转换为设备单位，以便它可以传递给本机方法以返回准确的监视器指针需要设备坐标 MonitorFromPoint。

### <a name="classes-of-issues"></a>类的问题
用于 Visual Studio 启用 PMA 模式后，UI 可能几种常见方式复制问题。 大多数，如果不是全部，这些问题可能在任何 Visual Studio 支持的 UI 框架中发生。 此外，这些问题也可能在当混合模式 DPI 缩放方案中托管一个用户界面 (请参阅 Windows[文档](https://docs.microsoft.com/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)若要了解详细信息)。 

#### <a name="win32-window-creation"></a>创建 Win32 窗口
使用创建时 windows CreateWindow() 或 CreateWindowEx()，一种常见模式是坐标 (0，0) 处创建窗口 （主显示器的左上角），然后将其移动到其最终位置。 但是，这样做可能会导致窗口以触发 DPI 更改消息或事件时，它可以重新触发其他 UI 消息或事件，并最终会导致意外的行为或呈现。

#### <a name="wpf-element-placement"></a>WPF 元素放置
移动时使用旧 Microsoft.VisualStudio.Utilities.Dpi.DpiHelper 的 WPF 元素，左上角坐标可能不会计算正确元素是在非主 DPI。

#### <a name="serialization-of-ui-element-sizes-or-positions"></a>序列化的 UI 元素大小或位置
当在不同的 DPI 上下文比它已存储在恢复时 UI 大小或位置 （如果另存为设备单位） 时，它将定位，大小不正确。 这是因为设备单位具有固有的 DPI 关系。

#### <a name="incorrect-scaling"></a>不正确缩放
但当移动到具有不同 DPI 显示器，它们不重新缩放，因此，其内容，该怎么办太大或太小，在主 DPI 上创建的 UI 元素将正确，缩放。

#### <a name="incorrect-bounding"></a>不正确的边界
同样，到扩展的问题，UI 元素将计算其边界正确地在其主 DPI 上下文中，但移动到非主 DPI 时，它们将不能正确计算的新边界。 在这种情况下，内容的窗口最终会太小或太大，相比宿主 UI，这会导致空的空间或剪辑。

#### <a name="drag--drop"></a>拖放
每当在混合模式 DPI 方案 （例如不同的 UI 元素在不同的 DPI 感知模式呈现） 的拖放坐标可能是错误计算，导致最终存放位置最终会不正确。

#### <a name="out-of-process-ui"></a>进程外 UI
一些 UI 创建扩展的进程，如果创建外部过程在比 Visual Studio 不同 DPI 感知模式下，这可能会带来的任何以前的呈现问题。

#### <a name="windows-forms-controls-images-or-layouts-rendered-incorrectly"></a>Windows 窗体控件、 图像或未正确呈现的布局
并非所有的 Windows 窗体内容支持 PMA 模式。 因此，可能会看到呈现问题不正确的布局或缩放。 可能的解决方案在这种情况下是以显式呈现在"系统识别"DpiAwarenessContext 中的 Windows 窗体内容 (请参阅[到特定 DpiAwarenessContext 强制控件](#forcing-a-control-into-a-specific-dpiawarenesscontext))。

#### <a name="windows-forms-controls-or-windows-not-displaying"></a>Windows 窗体控件或 windows 未显示
此问题的主要原因之一是开发人员尝试重新设置父级控件或具有一个 DpiAwarenessContext 到窗口与不同 DpiAwarenessContext 窗口。

下图显示当前**默认**中作为父级 windows 的 Windows 操作系统限制：

![正确设置父级行为的屏幕截图](../../extensibility/ux-guidelines/media/PMA-parenting-behavior.PNG)

> [!Note]
> 您可以通过设置线程承载行为更改此行为 (请参阅[DpiHostinBehaviour](https://docs.microsoft.com/windows/desktop/api/windef/ne-windef-dpi_hosting_behavior))。

因此，如果设置不受支持模式之间的父子关系，它将失败，并且控件或窗口可能不会按预期方式呈现。

### <a name="diagnosing-issues"></a>诊断问题
有许多标识 PMA 相关的问题时需要考虑的因素： 

1. 执行 UI 或预期逻辑的 API 或设备值。
    - WPF UI 和 Api 通常使用逻辑值 （但并非总是如此）
    - Win32 UI 和 Api 通常使用设备值

2. 这些值来自哪里？
    - 如果从其他用户界面或 API 收到的值，是其传递设备或逻辑值。
    - 如果从多个源中接收值，则执行它们都使用/预期相同类型的值或转换需要进行混合和匹配？

3. UI 中使用的常量和何种窗体这些用户位于？

4. 线程是正确的值的 DPI 上下文中接收？
    - 若要启用混合 DPI 托管的更改通常应将代码路径放在正确的环境，但是，主消息循环或事件流外部完成的工作可能会执行的错误的 DPI 上下文中。

5. 值交叉 DPI 上下文边界？
    - 拖放是坐标与 DPI 上下文的位置的常见情况。 窗口尝试执行正确的操作，但在某些情况下，宿主 UI 可能需要执行转换操作，以确保匹配的上下文边界。

### <a name="pma-nuget-package"></a>PMA NuGet 包
可以在找到新 DpiAwarness 库[Microsoft.VisualStudio.DpiAwareness](https://www.nuget.org/packages/Microsoft.VisualStudio.DpiAwareness/) NuGet 包。

### <a name="recommended-tools"></a>建议的工具
以下工具可帮助跨不同的 UI 堆栈支持的 Visual Studio 的一些调试 PMA 相关的问题。

#### <a name="snoop"></a>搜索
Snoop 是带有内置的 Visual Studio XAML 工具不会有一些额外功能的 XAML 调试工具。 此外，Snoop 不需要主动调试 Visual Studio，以便能够查看和调整其 WPF UI。 Snoop 也可用于诊断 PMA 问题的两种主要方法用于验证逻辑位置坐标或大小指定边界内，用于验证 UI 具有正确的 DPI。
 
#### <a name="visual-studio-xaml-tools"></a>Visual Studio XAML 工具
如 Snoop，Visual Studio 中的 XAML 工具可以帮助诊断 PMA 问题。 一旦找到可能的原因，可以设置断点，并使用实时可视化树窗口中，以及调试窗口中，检查 UI 边界和当前的 DPI。

## <a name="strategies-for-fixing-pma-issues"></a>修复 PMA 问题的策略
### <a name="replacing-dpihelper-calls"></a>将替换为 DpiHelper 调用
在大多数情况下，在 PMA 模式下修复 UI 问题归结为将替换为在托管代码中的调用到旧*Microsoft.VisualStudio.Utilities.Dpi.DpiHelper*和*Microsoft.VisualStudio.PlatformUI.DpiHelper*类，通过调用新*Microsoft.VisualStudio.Utilities.DpiAwareness*帮助器类。 

```cs
// Remove this kind of use:
Point deviceTopLeft = new Point(window.Left, window.Top).LogicalToDeviceUnits();

// Replace with this use:
Point deviceTopLeft = window.LogicalToDevicePoint(new Point(window.Left, window.Top));
```

对于本机代码，它所需替换为对旧*VsUI::CDpiHelper*通过调用新类*VsUI::CDpiAwareness*类。 

```cpp
// Remove this kind of use:
int cx = VsUI::DpiHelper::LogicalToDeviceUnitsX(m_cxS);
int cy = VsUI::DpiHelper::LogicalToDeviceUnitsY(m_cyS);

// Replace with this use:
int cx = m_cxS;
int cy = m_cyS;
VsUI::CDpiAwareness::LogicalToDeviceUnitsX(m_hwnd, &cx);
VsUI::CDpiAwareness::LogicalToDeviceUnitsY(m_hwnd, &cy);
```

新的 DpiAwareness 和 CDpiAwareness 类提供了相同单位转换帮助程序 DpiHelper 类但需要额外的输入的参数： 要用于为引用的转换操作的 UI 元素。 务必要注意的图像缩放帮助器执行操作中不存在的新 DpiAwareness/CDpiAwareness 帮助程序，并根据需要[ImageService](https://docs.microsoft.com/visualstudio/extensibility/image-service-and-catalog?view=vs-2019)应改为使用。

托管的 DpiAwareness 类为 WPF 视觉对象、 Windows 窗体控件和 Win32 Hwnd 和 HMONITORs （这种形式的 IntPtrs），提供了本机 CDpiAwareness 类产品/服务 HWND 和 HMONITOR 帮助器时的帮助程序。

### <a name="windows-forms-dialogs-windows-or-controls-displayed-in-the-wrong-dpiawarenesscontext"></a>Windows Forms 对话框、 windows 或错误 DpiAwarenessContext 中显示的控件
即使在之后使用 （由于 Windows 默认行为） 的不同 DpiAwarenessContexts windows 成功设置父级，用户可能仍会看到扩展问题以 windows 使用不同的 DpiAwarenessContexts 缩放以不同的方式。 因此，用户可能会看到模糊对齐/文本或图像 UI 上的问题。

解决方案是在应用程序中设置所有窗口和控件的正确 DpiAwarenessContext 作用域。

### <a name="top-level-mixed-mode-tlmm-dialogs"></a>顶级混合的模式 (TLMM) 对话框
在创建时如模式对话框的顶级窗口，务必确保处于正确状态窗口 （和其句柄） 之前所创建线程。 线程可以放入系统深刻的认识，在本机使用 CDpiScope 帮助器或中的 DpiAwareness.EnterDpiScope 帮助程序管理。 （TLMM 通常应在非 WPF 对话框/windows 上。）

### <a name="child-level-mixed-mode-clmm"></a>子级别混合的模式 (CLMM)
默认情况下，子窗口接收当前线程 DPI 感知上下文如果创建没有父级或父级的 DPI 感知上下文时使用父创建。 若要创建不同的 DPI 感知上下文与其父与子，线程可以放入所需的 DPI 感知上下文。 然后可以没有父级的情况下创建子并将其手动重新设定到父窗口。

#### <a name="clmm-issues"></a>CLMM 问题
在正确的 DPI 感知环境应已运行大部分的主消息循环或事件链中进行 UI 计算工作。 但是，如果坐标或大小调整计算完成这些主要的工作流外部 （例如，期间是空闲时间的任务，或关闭 UI 线程，当前的 DPI 感知上下文可能不正确，导致 UI 被错放或错误大小调整问题。 用户界面将线程放入正确的状态的工作通常解决了问题。
 
#### <a name="opting-out-of-clmm"></a>选择退出 CLMM
如果要迁移非 WPF 工具窗口以完全支持 PMA，它将需要选择退出 CLMM。 若要执行此操作，需要实现的新接口：IVsDpiAware。

C#：

```cs
[InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
public interface IVsDpiAeware
{
    [ComAliasName("Microsoft.VisualStudio.Shell.Interop.VSDPIMode")]
    uint Mode {get;}
}
```
 
C++：

```cpp
IVsDpiAware : public IUnknown
{
    public:
        HRRESULT STDMETHODCALLTYPE get_Mode(__RCP__out VSDPIMODE *dwMode);
};
```

对于托管语言，实现此接口的最佳位置是在同一类派生自*Microsoft.VisualStudio.Shell.ToolWindowPane*。 有关C++，若要实现此接口的最佳位置是在同一个类实现*IVsWindowPane*从 vsshell.h。

模式属性的接口上返回的值是 __VSDPIMODE （和强制转换为 uint 中托管）：

```cs
enum __VSDPIMODE
{
    VSDM_Unaware    = 0x01,
    VSDM_System     = 0x02,
    VSDM_PerMonitor = 0x03,
}
```

- 不知道意味着需要处理 96 DPI，工具窗口时，Windows 将处理的所有其他 Dpi 缩放。 生成的内容进行轻微的模糊上。
- 系统意味着需要处理的 DPI 的主要工具窗口显示 DPI。 任何具有匹配的 DPI 显示器将看起来正常，但如果 DPI 不同，或在会话期间发生更改，Windows 将处理的规模和它将是轻微的模糊。
- PerMonitor 意味着工具窗口需要处理所有显示器上的所有 Dpi 时所使用的 DPI 发生更改。

> [!NOTE]
> Visual Studio 仅支持 PerMonitorV2 意识，因此 PerMonitor 枚举值转换为的 DPI_AWARENESS_CONTEXT_PER_MONITOR_AWARE_V2 Windows 值。

#### <a name="forcing-a-control-into-a-specific-dpiawarenesscontext"></a>到特定 DpiAwarenessContext 强制控件
未在更新以支持 PMA 模式的旧 UI 可能仍需要在 PMA 模式下运行 Visual Studio 期间的细微调整。 一个此类修补程序需确保在正确 DpiAwarenessContext 中创建 UI。 若要强制转到特定 DpiAwarenessContext UI，可以输入下面的代码具有的 DPI 作用域：

C#：

```cs
using (DpiAwareness.EnterDpiScope(DpiAwarenessContext.SystemAware))
{
    Form form = new MyForm();
    form.ShowDialog();
}
```

C++：

```cpp
void MyClass::ShowDialog()
{
    VsUI::CDpiScope dpiScope(DPI_AWARENESS_CONTEXT_SYSTEM_AWARE);
    HWND hwnd = ::CreateWindow(...);
}
```

> [!NOTE]
> 强制 DpiAwarenessContext 仅适用于非 WPF UI 和顶级 WPF 对话框。 当创建 WPF UI 是只要内容插入到 WPF UI 树内的工具窗口或设计器中，托管时，它将转换为当前进程 DpiAwarenessContext。

## <a name="known-issues"></a>已知问题
### <a name="windows-forms"></a>Windows 窗体

若要优化的新混合方案，Windows 窗体更改如何创建控件和窗口时未显式设置它们的父级。 更早版本，而无需显式父控件用作控件或窗口正在创建的临时父级内部"停车窗口"。 

在.NET 4.8 之前出现一个"停车窗口"，可在窗口的创建时从当前线程 DPI 感知上下文获取其 DpiAwarenessContext。 控件的句柄创建将由应用程序开发人员到预期最终/父父级时，任何没有父级的控件继承为停车窗口相同 DpiAwarenessContext。 如果"停车窗口"具有更高版本 DpiAwarenessContext 比最终父窗口，这将导致基于时间的故障。

截至.NET 4.8，现在有了一个"停车"用于窗口已遇到每个 DpiAwarenessContext。 其他主要区别是创建控件时，不是在创建了句柄时，缓存用于控制 DpiAwarenessContext。 这意味着总体最终行为是相同的但可以打开以前是基于时间的问题成为一致的问题。 它还使应用程序开发人员更多确定性行为用于编写其 UI 代码，并正确地将其范围设置。
