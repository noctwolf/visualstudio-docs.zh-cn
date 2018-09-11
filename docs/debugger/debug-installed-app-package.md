---
title: 调试安装的应用包 (UWP) |Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 07/17/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.remote.connection
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- app package, debug
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 291f24c6ffdf885cf3d24c5ff163c2f4f911d7ce
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279545"
---
# <a name="debug-an-installed-app-package-in-visual-studio-uwp"></a>调试 Visual Studio (UWP) 中的已安装的应用程序包

可以通过单击来调试任何已安装的应用程序包**调试 > 其他调试目标 > 调试安装的应用程序包**。 此调试方法有针对通用 Windows 应用 (UWP) 在这些设备上：

* Windows 10 （不支持在电话上）
* XBox
* HoloLens
* IoT

有关这些功能的详细信息，请参阅博客文章上的更新[调试已安装的应用包](https://blogs.msdn.microsoft.com/devops/2016/03/30/updates-for-debugging-installed-app-packages-in-visual-studio-2015-update-2/)和在 post[构建通用 Windows 应用 (UWP)](https://blogs.msdn.microsoft.com/visualstudio/2016/08/02/universal-windows-apps-targeting-windows-10-anniversary-sdk/)。

## <a name="debug-an-installed-app-package-or-running-app-on-a-local-machine-or-device"></a>调试安装的应用包或在本地计算机或设备上运行的应用

1. 在 Visual Studio 中打开 UWP 项目后，单击**调试 > 其他调试目标 > 调试安装的应用程序包**。

2. 选择任一**本地计算机**或**设备**。

     如果愿意**设备**，计算机必须以物理方式连接到 Windows 10 设备。

     ![DebugInstalledAppPackage](../debugger/media/debug-installed-app-pkg.png "DebugInstalledAppPackage")

     当前正在运行安装应用包都将出现下的**运行**节点。 已安装的应用包不运行显示向上**未运行**。

3. 选择你想要调试时所应用的名称**运行**或**未在运行**，然后选择**启动**或者，如果已在运行该应用程序，选择**附加**.

     如果选择**不启动，但在启动时调试我的代码**，这会导致 Visual Studio 调试器附加到您的应用程序时在自定义时启动它。 这是调试中的控制路径的有效途径[不同的启动方法](/windows/uwp/xbox-apps/automate-launching-uwp-apps)，如使用自定义参数的协议激活。

> [!NOTE]
> Visual Studio 还可以通过选择附加到任何正在运行的 UWP 应用进程**调试**，然后**附加到进程**。 将附加到正在运行的进程不需要原始的 Visual Studio 项目中，但加载进程的符号将起到显著作用调试不含的原始代码的进程时。
  
## <a name="remote"></a> 调试远程计算机上已安装或正在运行的应用程序 

当第一次调试远程计算机上安装的应用包时，Visual Studio 安装你的目标设备的远程工具的正确版本。 Windows 10 计算机、 XBox、 HoloLens 或 IoT 设备，必须为你的目标设备。

1. 在 Windows 10 设备上启用[开发人员模式](/windows/uwp/get-started/enable-your-device-for-development)。

2. 如果要连接到远程电脑手动首次运行前的创建者的更新版本的 Windows 10[安装并启动远程调试器](../debugger/remote-debugging.md)。

     对于 XBox、 HoloLens 或 IoT 设备和运行 Windows 10 创意者更新的 Windows 设备，您不必手动安装远程调试器。 部署应用时，将自动安装远程工具。

3. 单击**调试 > 其他调试目标 > 调试安装的应用程序包**。

4. 从第一个下拉列表中，选择**远程计算机**。

5. 键入名称或你想要将附加到计算机的 IP 地址。

     ![ChooseRemoteComputer](../debugger/media/debug-remote-app-pkg.png "ChooseRemoteComputer")

     如果您不能将附加使用计算机名称 (在选择后**启动**)，改为使用的 IP 地址。 用于 XBox、 HoloLens 或 IoT 设备的 IP 地址。

5. 选择如何通过选择中的一个选项来进行身份验证**身份验证模式**。

    对于大多数应用中，保留默认值**通用 （未加密的协议）**。

6. 选择你想要调试时所应用的名称**运行**或**未在运行**，然后选择**启动**或 （对于正在运行的应用）**附加**。

     如果选择**不启动，但在启动时调试我的代码**，这会导致 Visual Studio 调试器附加到你的应用程序包时在自定义时启动它。 这是调试中的控制路径的有效途径[不同的启动方法](/windows/uwp/xbox-apps/automate-launching-uwp-apps)，如使用自定义参数的协议激活。

     当第一次调试连接 XBox、 HoloLens 或 IoT 设备上安装的应用包时，Visual Studio 安装的目标设备的远程调试器的正确版本。 这可能需要一点时间，你将看到一条消息``Starting remote debugger``而发生这种情况。

     > [!NOTE]
> 在展示，XBox 或 HoloLens 设备将在附有如果它已在运行调试器的情况下重新启动应用。

UWP 应用的远程部署的高级选项的信息，请参阅 [部署和调试 UWP apps]((/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)。 
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中进行调试](../debugger/index.md)  
 [调试器功能简介](../debugger/debugger-feature-tour.md)  
 [远程调试](../debugger/remote-debugging.md)  
 [配置 Windows 防火墙以便进行远程调试](../debugger/configure-the-windows-firewall-for-remote-debugging.md)  
 [远程调试器端口分配](../debugger/remote-debugger-port-assignments.md)  
 [远程调试错误和疑难解答](../debugger/remote-debugging-errors-and-troubleshooting.md)