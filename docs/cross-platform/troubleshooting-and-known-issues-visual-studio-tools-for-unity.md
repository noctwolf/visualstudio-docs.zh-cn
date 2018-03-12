---
title: "疑难解答和已知问题 (Visual Studio Tools for Unity) | Microsoft Docs"
ms.custom: 
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-unity-tools
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f5db192-8d78-4627-bd07-dbbc803ac554
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: 95d1724561886e1bcfa9a870bdf3bdadb787f9e8
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2018
---
# <a name="troubleshooting-and-known-issues-visual-studio-tools-for-unity"></a>疑难解答和已知问题 (Visual Studio Tools for Unity)
本部分将介绍 Visual Studio Tools for Unity 常见问题的解决方案、已知问题的说明并了解如何通过报告错误来帮助改进 Visual Studio Tools for Unity。

## <a name="troubleshooting"></a>疑难解答
若要解决 Visual Studio Tools for Unity 的一些常见问题，请参阅以下各部分。

### <a name="visual-studio-crashes"></a>Visual Studio 崩溃
这可能是由 Visual Studio MEF 缓存损坏导致的。

应删除以下文件夹以重置 MEF 缓存（执行此操作之前请关闭 Visual Studio）：

```batch
%localappdata%\Microsoft\VisualStudio\<version>\ComponentModelCache
```

这样应该能够解决问题。 如果仍然有问题，请以管理员身份运行 Visual Studio 的开发人员命令提示，并使用以下命令：

```batch
 devenv /setup
```

### <a name="issues-with-vs2015-and-intellisense-or-code-coloration"></a>VS2015 和 IntelliSense 或代码着色出现问题。
应尝试将 Visual Studio 2015 升级到更新 3。

### <a name="visual-studio-hangs"></a>Visual Studio 挂起
Parse、FMOD、UMP (Universal Media Player)、ZFBrowser 或嵌入式浏览器等几个 Unity 插件使用本机线程。 插件在最后将本机线程附加到运行时，阻止了对操作系统的调用，这时就会出现问题。 这意味着 Unity 不能对调试程序（或域重载）和挂起中断该线程。

有一种解决方法适合 FMOD：通过传递 FMOD_STUDIO_INIT_SYNCHRONOUS_UPDATE 初始化[标记](https://www.fmod.org/docs/content/generated/FMOD_STUDIO_INITFLAGS.html)来禁用异步处理，并对主线程执行所有处理。

### <a name="incompatible-project-in-visual-studio"></a>Visual Studio 中的不兼容项目
首先，检查是否已将 Visual Studio 设置为 Unity 中的外部脚本编辑器（编辑/首选项/外部工具）。 然后检查 Unity 是否已安装 Visual Studio 插件（“帮助/关于”必须在底部显示一条类似于“已启用 Microsoft Visual Studio Tools for Unity”的消息）。 然后检查 Visual Studio 中是否已正确安装该扩展（“帮助/关于”）。

### <a name="assembly-reference-issues"></a>程序集引用问题
如果项目中存在复杂引用，或者如果希望能更好地控制此生成步骤，可以使用我们的 [API](../cross-platform/customize-project-files-created-by-vstu.md) 来操作生成的项目或解决方案内容。 也可以在 Unity 项目中使用[响应文件](https://docs.unity3d.com/Manual/PlatformDependentCompilation.html)，我们将对它们进行处理。

### <a name="breakpoints-with-a-warning"></a>带有警告的断点
如果 Visual Studio 无法找到特定断点的源位置，系统会在断点附近显示一条警告消息。 检查当前的 Unity 场景中是否已正确加载/使用你正在使用的行为。

### <a name="breakpoints-not-hit"></a>未命中断点
 检查当前的 Unity 场景中是否已正确加载/使用你正在使用的行为。 退出 Visual Studio 和 Unity，然后删除生成的所有文件（*.csproj、*.sln）和整个库文件夹。

### <a name="unable-to-attach"></a>无法附加
-   尝试暂时禁用防病毒软件，或同时为 VS 和 Unity 创建排除规则。
-   尝试暂时禁用防火墙，或创建规则，允许在 VS 和 Unity 之间建立 TCP/UDP 网络。
-   我们发现 Team Viewer 之类的程序会干扰进程检测，建议尝试暂时停用任何外部软件，看看是否有影响。
-   请勿重命名主要 Unity 可执行文件，因为 VSTU 只监视“Unity.exe”进程。

### <a name="unable-to-debug-android-players"></a>无法调试 Android 播放器
我们使用多播进行播放器检测（这是 Unity 使用的默认机制），但之后我们会使用常规 TCP 连接来附加调试器。 检测阶段是 Android 设备的主要问题。

USB 用于调试时速度非常快，但与 Unity 播放器发现机制不兼容。
Wifi 更通用，但与 USB 比起来非常慢，因为存在延迟。 我们已经了解，某些路由器或设备缺少正确多播支持（众所周知，Nexus 系列就存在这个问题）。

可以尝试使用 USB 执行以下操作，在连接的设备上查看打开的端口（让播放机正常运行，以便查看调试端口，始终采用 56xxx 格式）：

```shell
adb shell netstat
```

将端口转接到本地 PC：

```shell
adb forward tcp:56xxx tcp:56xxx
```

然后使用转接端口 127.0.0.1:56xxx 连接 VSTU。

### <a name="migrating-from-unityvs-to-visual-studio-tools-for-unity"></a>从 UnityVS 迁移到 Visual Studio Tools for Unity
 如果从 UnityVS 迁移到 Visual Studio Tools for Unity，将需要为你的 Unity 项目生成新的 Visual Studio 解决方案。

##### <a name="to-migrate-your-unity-project-from-unityvs-18-to-visual-studio-tools-for-unity-19"></a>若要将 Unity 项目从 UnityVS 1.8 迁移到 Visual Studio Tools for Unity 1.9

1.  从 Unity 项目中将旧的解决方案和项目文件删除。 在 Unity 项目的根目录中，找到 Visual Studio .sln 和 .*proj 文件并将其全部删除。

2.  将 Visual Studio Tools for Unity 包导入 Unity 项目中。 有关如何导入 VSTU 包的信息，请参阅 [入门](../cross-platform/getting-started-with-visual-studio-tools-for-unity.md) 页面上的“配置 Visual Studio Tools for Unity”。

3.  生成新的解决方案和项目文件。 如果想要立即生成它们，则在 Unity 编辑器中的主菜单上，选择“Visual Studio Tools” 、“生成项目文件” 。 或者如果愿意，可以跳过此步骤；当选择“Visual Studio Tools” 、“在 Visual Studio 中打开” 时，Visual Studio Tools for Unity 会自动生成新的文件。

### <a name="on-windows-visual-studio-asks-to-download-the-unity-target-framework"></a>在 Windows 上，Visual Studio 会要求下载 Unity 目标框架
 Visual Studio Tools for Unity 要求安装 .net framework 3.5（默认情况下 Windows 8 或 10 上未安装）。 若要解决此问题，请按照说明下载并安装 .net framework 3.5。

## <a name="known-issues"></a>已知问题
 在 Visual Studio Tools for Unity 中存在一些已知问题，是由调试器与 Unity 的旧版本的 C# 编译器的交互方式导致的。 我们正设法帮助解决这些问题，但在此期间，你可能会遇到以下问题：

-   在调试时，Unity 有时会崩溃。

-   在调试时，Unity 有时会冻结。

-   有时单步执行和跳出方法的方式不正确，尤其是在迭代器中或在 switch 语句内。

## <a name="reporting-errors"></a>报告错误
 请在遇到崩溃、冻结或其他错误时发送错误报告以帮助我们改进 Visual Studio Tools for Unity 的质量。 这可以帮助我们调查并修复 Visual Studio Tools for Unity 中的问题。 谢谢！

### <a name="how-to-report-an-error-when-visual-studio-freezes"></a>如何在 Visual Studio 冻结时报告错误
 有报告表明使用 Visual Studio Tools for Unity 进行调试时 Visual Studio 有时会冻结，但我们需要更多的数据来了解这个问题。 你可以通过执行下面的步骤来帮助我们调查。

##### <a name="to-report-that-visual-studio-freezes-while-debugging-with-visual-studio-tools-for-unity"></a>报告使用 Visual Studio Tools for Unity 进行调试时 Visual Studio 会冻结

在 Windows 上：

1.  打开 Visual Studio 的新实例。

2.  打开“附加到进程”对话框。 在 Visual Studio 的新实例中的主菜单上，选择“调试” 、“附加到进程” 。

3.  将调试器附加到 Visual Studio 的已冻结的实例。 在“附加到进程”  对话框中，从“可用进程”  表中选择 Visual Studio 的已冻结实例，然后选择“附加”  按钮。

4.  暂停调试器。 在 Visual Studio 的新实例中的主菜单上，依次选择“调试”、“全部中断”或只需按 Ctrl + Alt + Break 即可。

5.  创建线程转储。 在命令窗口中，输入以下命令并按 Enter：

    ```powershell
    Debug.ListCallStack /AllThreads /ShowExternalCode
    ```

    你可能首先需要使“命令”  窗口可见。 在 Visual Studio 中的主菜单上，选择“视图” 、“其他窗口” 、“命令窗口” 。

在 Mac 上：

1. 打开终端并获取 Visual Studio for Mac 的 PID：

    ```shell
    ps aux | grep "[V]isual Studio.app"
    ```

1. 启动 lldb 调试程序：

    ```shell
    lldb
    ```

1. 使用 PID 附加到 Visual Studio for Mac 实例：

    ```shell
    process attach --pid THE_PID_OF_THE_VSFM_PROCESS
    ```

1. 检索所有线程的 stacktrace：

    ```shell
    bt all
    ```

最后，将线程转储以及 Visual Studio 冻结时你正在执行的操作的说明一起发送到 [vstusp@microsoft.com](mailto:vstusp@microsoft.com)。
