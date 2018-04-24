---
title: Visual Studio 中启动的 UWP 应用的调试会话 |Microsoft 文档
ms.custom: ''
ms.date: 01/04/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- VC.Project.IVCAppHostRemoteDebugPageObject.MachineName
- VC.Project.IVCAppHostRemoteDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostTetheredDebugPageObject.DebuggerType
- VC.Project.IVCAppHostLocalDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostRemoteDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.DebuggerType
- ImmersiveProjects.Properties.Debug
- VC.Project.IVCAppHostTetheredDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostLocalDebugPageObject.AllowLocalNetworkLoopback
- AppPackage.Properties.Debug
- VC.Project.IVCAppHostRemoteDebugPageObject.Authentication
- VC.Project.IVCAppHostRemoteDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.BreakpointBehavior
- vs.debug.installedapppackagelauncher
- vs.debug.error.wwahost_scriptdebuggingdisabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: b298e2b17f1aa8805e0ab896c6978744c6c3bd53
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="start-a-debugging-session-for-a-uwp-app-in-visual-studio"></a>Visual Studio 中启动的 UWP 应用的调试会话
  
 本主题介绍如何启动调试会话用 XAML 和 Visual c + +、 Visual C# 或 Visual Basic 中，编写的 UWP 应用程序和用 HTML 和 JavaScript 编写的 UWP 应用。 调试应用程序涉及配置调试会话和选择启动应用程序的方式。  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a> 启动调试的简单方法  
  
1.  在 Visual Studio 中打开应用程序解决方案。  
  
2.  按 F5。  
  
 Visual Studio 生成并启动附有调试器的应用程序。 持续执行至抵达某个断点、手动暂停执行、发生无法处理的异常或应用程序结束为止。  
  
##  <a name="BKMK_Choose_the_build_configuration_options"></a> 选择生成配置选项  
  
1.   下拉列表中下一步**启动调试**上调试器按钮**标准**工具栏上，选择**调试**。  
  
2.  从 **“平台”** 列表中选择要生成的目标平台。  
  
##  <a name="BKMK_Choose_the_deployment_target"></a> 选择部署目标  
  
你可以部署和调试在 Visual Studio 计算机、 连接的设备、 本地计算机、 远程设备或仿真程序上的 Visual Studio 模拟器上的 UWP 应用。 从下拉列表中选择部署目标，右侧**平台**上调试器目标**标准**工具栏。
  
![选择部署目标](../debugger/media/vsrun_select_target_device.png)  
  
选择以下某个选项：  
  
|||  
|-|-|  
|**本地计算机**|在本地计算机上的当前会话中调试应用程序。|  
|**模拟器**|调试适用于 UWP 应用的 Visual Studio 模拟器中应用程序。 模拟器是一个桌面窗口，使您能够调试设备功能，如触摸手势和设备旋转-可能无法在本地计算机上使用。 此选项才可用如果你的应用**目标平台最小值。版本**小于或等于您的开发计算机上的操作系统。 请参阅[在模拟器中运行的 UWP 应用](../debugger/run-windows-store-apps-in-the-simulator.md)。|  
|**远程计算机**|在通过 Intranet 连接到本地计算机或使用以太网电缆直接连接到本地计算机的设备上调试应用程序。 若要进行远程调试，Visual Studio 远程工具必须是远程设备上安装并运行。 请参阅[远程计算机上运行的 UWP 应用](../debugger/run-windows-store-apps-on-a-remote-machine.md)。|  
|**设备**|调试连接了 USB 的设备上的应用。 设备必须是开发人员解锁，而且必须解锁屏幕。|  
|**移动仿真程序**|使用的模拟器名称中指定的配置启动仿真程序，部署该应用，并开始调试。 仿真程序是仅在启用 HYPER-V 计算机上可用。|  

##  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a> 选择其他调试选项  

如果你需要配置其他调试选项，打开项目的属性页。
  
1.  在“解决方案资源管理器”中，选择项目。 在快捷菜单中，选择 **“属性”**。  
  
2.  执行此项可打开项目的调试属性页：  
  
    -   对于 Visual C# 和 Visual Basic 应用程序，选择 **“调试”**。  
  
         ![C&#35; &#47; VB 项目调试属性页](../debugger/media/dbg_csvb_debugpropertypage.png)  
  
    -   对于 Visual c + + 和 JavaScript 的应用程序中，展开**配置属性**节点，然后选择**调试**。  
  
         ![C&#43; &#43; UWP 应用调试属性页](../debugger/media/dbg_cpp_debugpropertypage.png)  

###  <a name="BKMK_Choose_the_debugger_to_use"></a> 选择要使用的调试器  
默认情况下，Visual Studio 调试 C# 和 Visual Basic 应用程序中的托管代码。 对于 C# 和 Visual Basic 应用程序，可选择同时调试应用程序中的托管和本机 C/C++ 代码。 在 c + + 应用中，Visual Studio 默认情况下调试本机代码。 在 JavaScript 应用中，Visual Studio 默认情况下调试脚本。 
  
针对 c + + 应用和 JavaScript，你可以选择调试组件中你的应用程序，而不是，或调试本机代码的特定类型的代码。 在应用程序项目的 **“调试”** 属性页上 **“调试器类型”** 列表中指定要调试的代码。  
  
从 **“应用程序进程”** 列表中选择以下这些调试器之一：  
  
|||  
|-|-|  
|**仅限托管**|调试应用程序中的托管代码。 忽略 JavaScript 代码和本机 C/C++ 代码。|  
|**仅限本机**|调试应用程序中的本机 C/C++ 代码。 忽略托管代码和 JavaScript 代码。|  
|**混合(托管和本机)**|调试应用程序中的本机 C/C++ 代码和托管代码。 忽略 JavaScript 代码。 在 c + + 项目中，此选项称为**（托管和本机）**。|  
|**仅限脚本**|调试应用程序中的 JavaScript 代码。 忽略托管代码和本机代码。|  
|**脚本和本机**|调试本机 C/c + + 代码和应用程序中的 JavaScript 代码。 忽略托管的代码。 在仅限 c + + 项目中可用。|  
|**仅限 GPU (c + + AMP)**|调试在图形处理单元 (GPU) 上运行的本机 C++ 代码。 在仅限 c + + 项目中可用。|  

在 C# 和 Visual Basic 应用中，你还可以设置相同**调试器类型**是项目的一部分的任何后台任务的值。
  
###  <a name="BKMK__Optional__Delay_starting_the_debug_session"></a> （可选）推迟启动调试会话  
 默认情况下，启动调试后，Visual Studio 将立即启动应用程序。 也可启动调试会话但推迟启动应用程序。 选择此选项后，从“开始”屏幕或由激活协定启动应用程序时或者其他进程或方法启动应用程序时，将在调试器中启动应用程序。 如果要在应用程序未运行时调试后台任务，则还需延迟应用程序的启动。  
  
 若要推迟启动应用程序，可：  
  
-   对于 Visual C# 和 Visual Basic 应用程序，在 **“调试”** 属性页上选中 **“不启动，但在启动时调试代码”** 。  
  
-   对于 Visual c + + 和 JavaScript 应用，选择**否**从**启动应用程序**列表上**调试**属性页。  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a> （可选）禁用网络环回  
  
 出于安全原因，不允许以标准方式安装的 UWP 应用进行到设备安装的网络调用。 默认情况下，Visual Studio 部署功能为所部署的应用程序创建此规则的例外。 通过此例外，在一台计算机上即可测试通信过程。 提交你的 Microsoft 应用商店应用之前，应测试不例外的情况下应用。  
  
 若要移除网络环回例外，请执行以下操作：  
  
-   对于 Visual C# 和 Visual Basic 应用程序，清除**允许本地网络环回**上的复选框**调试**属性页。  
  
-   对于 Visual c + + 和 JavaScript 应用，选择**否**从**允许本地网络环回**列表上**调试**属性页。  
  
###  <a name="BKMK__Optional__Reinstall_the_app_when_you_start_debugging"></a> （可选）在开始调试时重新安装应用程序  
 若要诊断 Visual C# 或 Visual Basic 应用程序的安装和初始配置问题，请选择 **“调试”** 属性页上的 **“卸载并重新安装我的程序包”**  以在启动调试时重新创建原始安装。 此选项不适用于 Visual c + + 和 JavaScript 项目。  
  
###  <a name="BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger"></a> （可选）禁用身份验证要求以启动远程调试器  
  
 默认情况下，你必须提供凭据才能运行远程调试器，当你选择**远程计算机**作为部署目标。
  
> [!IMPORTANT]
>  你可以选择无身份验证运行远程调试器，但强烈建议不要使用此模式。 在此模式下运行时，无法保证网络安全。 只有在确认网络不会受到恶意代码或恶意流量，请选择无身份验证。  
  
 若有移除身份验证要求，请执行以下操作：  
  
1.  对于 Visual C# 和 Visual Basic 应用，选择**远程计算机**作为**目标设备**上**调试**属性页，然后将设置**身份验证模式**到**无**或**世界 （未加密的协议）**。
  
2.  对于 Visual c + + 和 JavaScript 应用，选择**远程计算机**作为**目标设备**上**调试**属性页，然后将设置**要求身份验证**到**无**或**世界 （未加密的协议）**。  

    **世界 （未加密的协议）**要部署到远程设备时使用。 目前，这是为 IoT 设备、 Xbox 设备和 HoloLens 设备，以及创建者更新或更高版本的电脑。 仅应在可信网络上使用世界 （未加密的协议）。 调试连接容易受到恶意用户就无法截获并且无法更改正在开发和远程计算机之间传递数据。  
  
##  <a name="BKMK_Start_the_debugging_session"></a> 启动调试会话  
  
###  <a name="BKMK_Start_debugging__F5_"></a> 启动调试 (F5)  
 当你选择**启动调试**(键盘： F5) 上**调试**菜单上，Visual Studio 附带调试器启动的应用。 持续执行至抵达某个断点、手动暂停执行、发生异常或应用程序结束为止。  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a> 启动调试 (F5)，但推迟启动应用程序  
 你可以将应用程序设置为在调试模式中运行，但通过调试器之外的方法启动应用程序。 例如，你可能需要调试从开始菜单中，你的应用启动，或者在不启动应用程序的情况下调试应用程序中的后台进程。 若要推迟启动应用程序，请执行此操作：  
  
-   上**调试**的应用程序的属性页 (**调试**中 Visual c + + 和 JavaScript)  
  
    -   对于 Visual C# 和 Visual Basic 应用程序，选中 **“不启动，但启动时调试代码”**。  
  
    -   对于 Visual c + + 和 JavaScript 应用，选择**是**从**启动应用程序**列表。  
  
-   选择**启动调试**上**调试**菜单 (键盘： F5)。  
  
-   从“开始”菜单、执行协定或由其他过程启动应用程序。  
  
 随后应用程序在调试模式下启动。 持续执行至抵达某个断点、手动暂停执行、发生无法处理的异常或应用程序结束为止。  
  
 有关调试后台任务的详细信息，请参阅[触发器挂起、 继续和后台适用于 UWP 应用的事件)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)。  
  
###  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a> 在调试器中启动已安装的应用程序  
在使用 F5 启动调试时，Visual Studio 会生成并部署应用程序，将应用程序设置为在调试模式中运行，然后启动应用程序。 若要开始在设备已安装的应用程序，使用**调试安装的应用程序包**对话框。 当需要调试已从 Microsoft 应用商店安装的应用程序，或在拥有应用程序中的源文件但没有应用的 Visual Studio 项目时，此过程非常有用。 例如，你的自定义生成系统可能不使用 Visual Studio 项目或解决方案。  
  
应用程序可安装在本地设备上，也可安装在远程设备上。  你可以立即启动应用程序，或将应用程序设置为当其通过其他进程或方法（如从“开始”菜单或通过激活协定）启动时在调试器中运行，也可以将应用程序设置为当需要在未启动应用程序的情况下调试后台进程时在调试模式中运行。 有关详细信息，请参阅[触发器挂起、 继续和后台适用于 UWP 应用的事件)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)。  
  
若要在调试器中启动安装的应用程序，选择**调试**，然后**其他调试目标**，，然后**调试安装的应用程序包**。 有关更多说明，请参阅[调试已安装的应用程序包](../debugger/debug-installed-app-package.md)。

###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> 将调试器附加到正在运行的 UWP 应用  

若要调试正在运行的 UWP 应用，选择**调试**，然后**其他调试目标**，，然后**调试安装的应用程序包**。 有关更多说明，请参阅[调试已安装的应用程序包](../debugger/debug-installed-app-package.md)。
  
###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> 将调试器附加到正在运行的 Windows 8.x 应用
 若要将调试器附加到 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 应用程序，必须使用可调式包管理器将应用程序设置为以调试模式运行。 可调式包管理器与远程工具安装 for Visual Studio。  
  
 当需要调试已安装的应用程序（如从 [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]安装的应用程序）时，将调试器附加到应用程序很有用。 在拥有应用程序的源文件，但没有应用程序的 Visual Studio 项目时，必须进行附加。 例如，你的自定义生成系统可能不使用 Visual Studio 项目或解决方案。  
  
 将调试器附加到应用程序需要执行以下这些步骤：  
  
1.  将应用程序设置为以调试模式运行。 必须在应用程序未运行时执行此操作。  
  
2.  启动该应用程序。 可从“开始”屏幕、执行协定或通过某些其他方法启动该应用程序。  
  
3.  将调试器附加到正在运行的应用程序。  
  
####  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a> 将应用程序设置为以调试模式运行  
  
1.  在装有该应用的设备上为 Visual Studio 安装远程工具。 请参阅[安装远程工具](../debugger/remote-debugging.md)。  
  
2.  在“开始”屏幕上，搜索 `Debuggable Package Manager` ，然后启动它。  
  
     随后显示 PowerShell 窗口，该窗口针对 AppxDebug cmdlet 进行了正确的配置。  
  
3.  若要能够调试应用程序，必须指定该应用程序的 PackageFullName 标识符。 若要查看包含 PackageFullName 的所有应用程序的列表，请在 PowerShell 提示符下键入 `Get-AppxPackage` 。  
  
4.  在 PowerShell 提示符下，输入 `Enable-AppxDebug` *PackageFullName* ，其中 *PackageFullName* 是应用的 PackageFullName 标识符。  
  
####  <a name="BKMK_Attach_the_debugger"></a> 附加调试器  
 若要附加调试器，请执行以下操作：  
  
1.  在 **“调试”** 菜单上选择 **“附加到进程”**。  
  
     出现 **“附加到进程”** 对话框。  
  
2.  若要附加到远程设备上的应用程序，请在 **“限定符”** 框中指定该远程设备。 你可以：  
  
    -   在 **“限定符”** 框中输入名称。  
  
    -   选择 **“限定符”** 框中的下拉箭头，然后从以前已附加到的设备的列表中选择该设备。  
  
    -   选择 **“查找”** ，从本地子网上设备的列表中选择该设备。  
  
3.  在 **“附加到”** 框中指定要调试的代码类型。  
  
     选择 **“选择”** ，然后执行下列操作之一：  
  
    -   选中 **“自动确定要调试的代码类型”**  
  
    -   选中 **“调试以下代码类型”** ，然后从列表中选择一个或多个类型。  
  
4.  在 **“可用进程”**  列表中，选择应用程序进程。  

    > [!NOTE]
    >  与其他应用程序类型，不同 JavaScript 应用使用 wwahost.exe 进程的实例中运行。 附加到应用时，如果其他 JavaScript 应用正在运行，你将需要了解应用正在运行的 wwahost.exe 的数字进程 ID (PID)。  
    >   
    >  处理此情形的最简单方法是关闭所有其他 JavaScript 应用。 否则，你可以在启动应用之前打开 Windows 任务管理器并记下 wwahost.exe 进程的 ID。 当指定要在附加的进程**可用进程**对话框中，应用的 wwahost.exe 将具有不同于你记录的 id。  
  
5.  选择 **“附加”**。  
  
 Visual Studio 将调试器附加到该进程。 持续执行至抵达某个断点、手动暂停执行、发生无法处理的异常或应用程序结束为止。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中调试应用](../debugger/debug-store-apps-in-visual-studio.md)   