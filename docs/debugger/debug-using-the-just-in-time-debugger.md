---
title: 使用实时调试器进行调试 |Microsoft Docs
ms.custom: ''
ms.date: 09/24/18
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: ee4d79a5-a1d2-4418-a93f-dd57a53e1836
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7a2e6cfbd6d26d575bab5d7592f320779ffd8888
ms.sourcegitcommit: 000cdd1e95dd02e99a7c7c1a34c2f8fba6a632af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47168391"
---
# <a name="debug-using-the-just-in-time-debugger-in-visual-studio"></a>在 Visual Studio 中使用实时调试器进行调试
在实时调试 Visual Studio 会自动启动 Visual Studio 之外运行的应用程序中发生异常或崩溃时。 这使您测试应用程序，如果未运行 Visual Studio，并开始使用 Visual Studio 进行调试时出现问题。

在实时调试适用于 Windows 桌面应用。 它并不适用于通用 Windows 应用，并不适用于本机应用程序，例如可视化工具中托管的托管代码。

> [!TIP]
> 如果只想知道如何响应实时中调试器对话框，请参阅[本主题](../debugger/just-in-time-debugging-in-visual-studio.md)。

##  <a name="BKMK_Enabling"></a> 启用或禁用在实时调试
可以启用或禁用在实时调试 Visual Studio**工具 > 选项**对话框。

#### <a name="to-enable-or-disable-just-in-time-debugging"></a>启用或禁用实时调试

1.  使用管理员特权打开 Visual Studio (右键单击并选择**以管理员身份运行**)。

    启用或禁用在实时调试会设置一个注册表项，并可能需要管理员权限来更改该密钥。

2. 在 **“工具”** 菜单上，单击 **“选项”**。

2.  在中**选项**对话框框中，展开**调试**节点。

3.  在中**调试**节点中，选择**中实时**。

    ![启用或禁用 JIT 调试](../debugger/media/dbg-jit-enable-or-disable.png "启用或禁用 JIT 调试")

4.  在中**这些类型的代码启用实时调试**框中，选择或清除相关的程序类型：**托管**，**本机**，或**脚本**.

5.  单击 **“确定”**。

    如果启用了实时中调试器，但你看不到它在应用程序崩溃或异常，请参阅[中实时调试错误](#jit_errors)。

即便在你的计算机中不再安装有 Visual Studio，仍可启用实时调试。 未安装 Visual Studio 时，不能禁用中实时从 Visual Studio 调试**选项**对话框。 对于这种情况，你可以通过编辑 Windows 注册表来禁用实时调试。

#### <a name="to-disable-just-in-time-debugging-by-editing-the-registry"></a>通过编辑注册表禁用实时调试

1.  上**启动**菜单中，搜索并运行 `regedit.exe`

2.  在中**注册表编辑器**窗口中，找到并删除以下注册表项：

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\。NETFramework\DbgManagedDebugger

    ![JIT 注册表项](../debugger/media/dbg-jit-registry.png "JIT 注册表项")

3.  如果您的计算机正在运行 64 位操作系统，如果还要删除下列注册表项：

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\。NETFramework\DbgManagedDebugger

4.  注意不要意外删除或更改任何其他注册表项。

5.  关闭**注册表编辑器**窗口。

#### <a name="to-enable-just-in-time-debugging-of-a-windows-form"></a>为 Windows 窗体启用实时调试

1.  默认情况下，Windows 窗体应用程序有一个顶级的异常处理程序，该处理程序允许程序在能够恢复时继续运行。 例如，如果你的 Windows 窗体应用程序引发未处理的异常，将看到一个对话框，如下所示：

     ![WindowsFormsUnhandledException](../debugger/media/windowsformsunhandledexception.png "WindowsFormsUnhandledException")

     启用在实时调试的 Windows 窗体应用程序，必须执行以下附加步骤：

2.  设置`jitDebugging`值设为`true`中`system.windows.form`部分中的 machine.config 或*\<应用程序名称 >*.exe.config 文件：

    ```xml
    <configuration>
        <system.windows.forms jitDebugging="true" />
    </configuration>
    ```

3.  在 C++ Windows 窗体应用程序中，还必须在 .config 文件或你的代码中设置 `DebuggableAttribute`。 如果使用编译[/Zi](/cpp/build/reference/z7-zi-zi-debug-information-format)且无[/Og](/cpp/build/reference/og-global-optimizations)，编译器会为您设置此属性。 然而，如果你想要调试非优化发布版本，则必须自行设置此项。 为此，你可以在应用程序的 AssemblyInfo.cpp 文件中添加下面一行：

    ```cpp
    [assembly:System::Diagnostics::DebuggableAttribute(true, true)];
    ```

     有关详细信息，请参阅<xref:System.Diagnostics.DebuggableAttribute>。

## <a name="a-namebkmkusingjituse-just-in-time-debugging"></a><a name="BKMK_Using_JIT">使用在实时调试
 本部分介绍可执行文件引发异常时，会发生什么情况。

 您必须具有 Visual Studio 安装，请遵循以下步骤。 如果未安装 Visual Studio，则可以下载免费[Visual Studio Community Edition](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=15)。

 请确保该时间只需调试[启用](#BKMK_Enabling)。

 出于本部分的目的，我们将在引发的 Visual Studio 中进行 C# 控制台应用程序[NullReferenceException](/dotnet/api/system.nullreferenceexception)。

 在 Visual Studio 中，创建一个 C# 控制台应用 (**文件 > 新建 > 项目 > Visual C# > 控制台应用程序**) 名为**ThrowsNullException**。 在 Visual Studio 中创建项目的详细信息，请参阅[演练： 创建简单应用程序](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)。

 在 Visual Studio 中打开项目，打开 Program.cs 文件。 将打印到控制台的行，然后引发 NullReferenceException 的以下代码替换为 main （） 方法：

```csharp
static void Main(string[] args)
{
    Console.WriteLine("we will now throw a NullReferenceException");
    throw new NullReferenceException("this is the exception thrown by the console app");
}
```

> [!IMPORTANT]
>  为了使此过程工作[发布配置](../debugger/how-to-set-debug-and-release-configurations.md)，需要关闭[仅我的代码](../debugger/just-my-code.md)。 在 Visual Studio 中，单击**工具 > 选项**。 在中**选项**对话框中，选择**调试**。 清除该复选框，从**启用 ' 仅我的代码**。

 生成解决方案 (在 Visual Studio 中，选择**生成 > 重新生成解决方案**)。 您可以选择调试或发布配置 (选择**调试**以获取完整调试体验)。 有关生成配置的详细信息，请参阅[了解生成配置](../ide/understanding-build-configurations.md)。

 生成过程将创建可执行文件 ThrowsNullException.exe。 你可以在其中创建 C# 项目的文件夹下找到它： **...\ThrowsNullException\ThrowsNullException\bin\Debug**或 **...\ThrowsNullException\ThrowsNullException\bin\Release**。

 双击 ThrowsNullException.exe。 应会看到如下的命令窗口：

 ![ThrowsNullExceptionConsole](../debugger/media/throwsnullexceptionconsole.png "ThrowsNullExceptionConsole")

 将在几秒钟后会显示一个错误窗口：

 ![ThrowsNullExceptionError](../debugger/media/throwsnullexceptionerror.png "ThrowsNullExceptionError")

 不要单击**取消**！ 将在几秒钟后，会看到两个按钮**调试**并**关闭程序**。 单击**调试**。

> [!CAUTION]
>  如果你的应用程序包含不受信任的代码，将显示一个带有一条安全警告对话框。 此对话框使可以决定是否继续调试。 在继续调试之前，请决定你是否信任相应代码。 代码是你自己编写的吗？ 你是否信任代码编写者？ 如果该应用程序正在远程计算机上运行，你是否认识进程的名称？ 即便该应用程序在本地运行，也不一定表示它是可信的应用程序。 请考虑在您的计算机上运行的恶意代码的可能性。 如果你决定，该代码您即将调试值得信任，请单击**调试**。 否则，请单击**不调试**。

 **Visual Studio 实时调试器**窗口将显示：

 ![JustInTimeDialog](../debugger/media/justintimedialog.png "JustInTimeDialog")

 下**可能的调试器**，您应该会看到**Microsoft Visual Studio 的新实例<available version>** 选择行。 如果已选择，请立即选择它。

 在窗口底部下**你想要使用所选的调试器进行调试？**，单击**是**。

 ThrowsNullException 项目可打开 Visual Studio 的新实例中与引发的异常的代码行处停止执行：

 ![NullReferenceSecondInstance](../debugger/media/nullreferencesecondinstance.png "NullReferenceSecondInstance")

 你可以开始调试在这里。 如果这是实际的应用程序，您需要找出原因代码抛出异常。

## <a name="jit_errors"></a> 在实时调试错误
 如果看不到对话框中，当程序出现故障，需要启用该功能时，这可能会由于您的计算机上的 Windows 错误报告设置。 请确保添加**禁用**对以下注册表项值，并将值设置为 1:

* HKLM\Software\Microsoft\Windows\Windows 错误报告
* HKLM\Software\WOW6432Node\Microsoft\Windows\Windows 错误报告
 
有关这些设置的详细信息，请参阅[。WER 设置](https://docs.microsoft.com/windows/desktop/wer/wer-settings)。

此外，可能会看到以下错误消息与在实时调试。

- **无法附加到崩溃进程。指定的程序不是 Windows 或 MS-DOS 程序。**

    当你尝试附加到以其他用户身份运行的进程时，将发生此错误。

    若要解决此问题，请启动 Visual Studio 中，打开**附加到进程**对话框从**调试**菜单中，并查找过程，你想要在调试**可用进程**列表。 如果不知道进程名称，看看**Visual Studio 实时调试器**对话框并记下进程 id。 选择中的过程**可用进程**列表中，单击**附加**。 在中**Visual Studio 实时调试器**对话框中，单击**否**以关闭对话框。

- **无法启动调试器，因为没有用户登录。**

    在没有用户登录到控制台的计算机中，如果实时调试尝试启动 Visual Studio，则会发生此错误。 因为没有用户登录，所以没有用户会话来显示“实时调试”对话框。

    要解决此问题，请登录到计算机。

- **未注册的类。**

    此错误指出：调试器尝试创建一个可能是因为安装问题而没有注册的 COM 类。

    若要解决此问题，请使用安装盘重新安装或修复 Visual Studio 安装。

## <a name="see-also"></a>请参阅
 [调试器安全](../debugger/debugger-security.md)[调试器基础知识](../debugger/getting-started-with-the-debugger.md)[中的实时，调试，Options Dialog Box](../debugger/just-in-time-debugging-options-dialog-box.md) [安全警告： 附加到不受信任的用户拥有的进程可以是危险。如果以下信息看上去可疑或者你无法确定，请勿附加到此进程](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md)
