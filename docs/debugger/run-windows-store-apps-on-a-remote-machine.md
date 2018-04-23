---
title: 在远程计算机上运行 UWP 应用 |Microsoft 文档
ms.custom: ''
ms.date: 01/05/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 0f6814d6-cd0d-49f3-b501-dea8c094b8ef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 2c09d29340584f3f6187175342fd1171dd59ba37
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="run-uwp-apps-on-a-remote-machine-in-visual-studio"></a>Visual Studio 中的远程计算机上运行 UWP 应用
  
若要在远程计算机上运行的 UWP 应用，则必须附加到该使用适用于 Visual Studio 远程工具。 远程工具，可以运行、 调试、 分析和测试在运行 Visual Studio 的第二个计算机在另一台设备运行的 UWP 应用。 当在 Visual Studio 计算机不支持特定于 UWP 应用，如触摸、 地理位置和真实方向的功能，在远程设备上运行可能特别有效。 本主题介绍配置和启动远程会话的过程。

在某些情况下，部署到远程设备时将自动安装远程工具。

- 对于运行创建者更新和更高版本的 Windows 10 电脑，将自动安装远程工具。
- 对于 Windows 10 Xbox、 IOT 和 HoloLens 设备，将会自动安装远程工具。
- 适用于 Windows Mobile 10，你必须以物理方式连接到手机，则必须启用[开发者模式](/windows/uwp/get-started/enable-your-device-for-development)并且你必须选择**设备**作为调试目标。 远程工具不需要或支持。

对于运行以前创建者的更新版本的 Windows 的 Windows 10 电脑，你必须安装远程工具在远程计算机上手动可以调试之前。 按照本主题中的说明。 
  
##  <a name="BKMK_Prerequisites"></a> 先决条件  
 在远程设备上进行调试：  
  
- 远程设备与 Visual Studio 计算机必须通过网络连接或通过 USB 或以太网电缆直接连接。 不支持通过 Internet 进行调试。  

- 必须启用[开发者模式](/windows/uwp/get-started/enable-your-device-for-development)。 
  
- 对于运行早于 Windows 10 创建者的更新版本的 Windows 10 的 Windows 10 电脑，您必须[安装和运行远程调试组件](#BKMK_download)。
  
##  <a name="BKMK_Security"></a> 安全性  
默认情况下，**世界 （未加密的协议）**在 Windows 10 上使用。 仅应在可信网络上使用此协议。 调试连接容易受到恶意用户就无法截获并且无法更改正在开发和远程计算机之间传递数据。
  
> [!WARNING]
>  没有无法保证网络安全身份验证模式设置为时**世界 （未加密的协议）**或**无**。 只有在确认网络不会遇到恶意通信的请选择这些模式。  
  
##  <a name="BKMK_DirectConnect"></a> 如何直接使用 USB 电缆进行连接 

在 Windows 10 中，你可以部署到连接了 USB 的设备通过选择**设备**而不是**远程计算机**作为部署目标 (可以执行此操作**标准**工具栏或在调试属性页）。

##  <a name="BKMK_ConnectVS"></a> 配置远程调试的 Visual Studio 项目  
 可在项目的属性中指定所连接到的远程计算机。 该过程因编程语言而有所不同。 您可以键入远程设备的网络名称也可以选择从**远程连接**对话框。  
  
 ![选择远程调试器连接对话框](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
 该对话框仅列出在 Visual Studio 计算机的本地子网上并且正在运行远程调试器的那些设备。  
  
> [!TIP]
>  如果连接到远程设备时遇到问题，则尝试访问设备的 IP 地址。 若要确定设备的 IP 地址，请打开命令窗口，然后键入 **ipconfig**。 随后将以 **IPv4 Address**为标题列出 IP 地址。  
  
###  <a name="BKMK_Choosing_the_remote_device_for_C__and_Visual_Basic_projects"></a> 选择 C# 和 Visual Basic 项目的远程设备  
  
1.  在解决方案资源管理器中选择项目名称，然后从快捷菜单中选择 **“属性”** 。  
  
2.  选择 **“调试”**。  
  
3.  从 **“目标设备”** 列表中选择 **“远程计算机”** 。  
  
4.  在 **“远程计算机”** 框中输入远程设备的网络名称，或选择 **“查找”** ，从 **“选择远程调试器连接”** 对话框中选择该设备。 

    ![管理项目属性以便进行远程调试](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
###  <a name="BKMK_Choosing_the_remote_device_for_JavaScript_and_C___projects"></a> 选择远程设备为 JavaScript 和 c + + 项目  
  
1.  在解决方案资源管理器中选择项目名称，然后从快捷菜单中选择 **“属性”** 。  
  
2.  展开 **“配置属性”** 节点，然后选择 **“调试”**。  
  
3.  从 **“要启动的调试器”** 列表中选择 **“远程调试器”** 。  
  
4.  在 **“计算机名称”** 框中输入远程设备的网络名称，或选择该框中的下箭头，从 **“选择远程调试器连接”** 对话框中选择该设备。  

    ![C&#43; &#43;项目属性以便进行远程调试](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")
  
## <a name="BKMK_download"></a> 下载并安装远程工具 （预创建者更新）

如果要将以前的创建者的更新版本的 Windows 10，然后按照这些说明。 否则，你可以跳过此部分。

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a> 设置远程调试器

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]  
  
##  <a name="BKMK_RunRemoteDebug"></a> 启动远程调试会话  
 开始、停止和导航远程调试会话的方法与进行本地会话相同。 在以前的创建者的更新版本的 Windows 10 中，确保在远程设备上运行远程调试监视器。  
  
 然后在 **“调试”** 菜单上，选择 **“启动调试”** （键盘：F5）。 项目会重新编译，然后部署到远程设备上并启动。 调试器在断点暂停执行，以使您可进入逐语句执行、逐过程执行和跳出代码。 选择 **“停止调试”** 以结束调试会话并关闭远程应用程序。
  
## <a name="see-also"></a>请参阅  
 [高级远程部署选项](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)  
 [使用 Visual Studio 测试 UWP 应用](../test/testing-store-apps-with-visual-studio.md)   
 [在 Visual Studio 中调试应用](../debugger/debug-store-apps-in-visual-studio.md)