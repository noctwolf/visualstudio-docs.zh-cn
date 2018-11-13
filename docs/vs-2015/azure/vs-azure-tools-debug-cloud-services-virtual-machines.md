---
title: 调试 Azure 云服务或在 Visual Studio 中的虚拟机 |Microsoft Docs
description: 调试 Visual Studio 中的云服务或虚拟机
author: mikejo5000
manager: douge
ms.assetid: 945e06e0-2100-41af-b218-72347367ddab
ms.topic: conceptual
ms.custom: vs-azure
ms.workload: azure-vs
ms.date: 11/11/2016
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.openlocfilehash: b2c67ce81a42df4a17761fcee2dcd2f8a67c4941
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001569"
---
# <a name="debugging-an-azure-cloud-service-or-virtual-machine-in-visual-studio"></a>调试 Azure 云服务或在 Visual Studio 中的虚拟机

Visual Studio 可以调试 Azure 云服务和虚拟机的不同选项。

## <a name="debug-your-cloud-service-on-your-local-computer"></a>调试在本地计算机上的云服务

您可以节省时间和资金，通过使用 Azure 计算模拟器调试本地计算机上的云服务。 通过本地调试服务，在部署之前，可以提高可靠性和性能而无需为计算时间付费。 但是，仅当你运行的云服务在 Azure 中出现某些错误本身。 如果启用远程调试，当你发布你的服务，然后将调试器附加到角色实例时，您可以调试这些错误。

该模拟器模拟 Azure 计算服务，并在本地环境中运行，以便可以测试和调试你的云服务，在部署之前。 在仿真程序处理角色实例的生命周期，并提供对模拟资源，如本地存储的访问。 当您调试或从 Visual Studio 中运行你的服务时，它自动作为后台应用程序中启动模拟器，然后将服务部署到仿真程序。 在仿真程序可用于在本地环境中运行时查看你的服务。 可以运行完整版或速成版的模拟器。 （从 Azure 2.3 开始，在模拟器的 express 版本是默认值。）请参阅[使用 Emulator Express 运行和调试云服务本地](vs-azure-tools-emulator-express-debug-run.md)。

### <a name="to-debug-your-cloud-service-on-your-local-computer"></a>若要调试在本地计算机上的云服务

1. 在菜单栏上依次选择**调试**，**开始调试**运行 Azure 云服务项目。 或者，可以按 F5。 您将看到一条消息，计算模拟器正在启动。 在仿真程序启动时，系统任务栏图标确认它。

    ![在系统任务栏中的 azure 仿真程序](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC783828.png)

2. 显示计算仿真程序用户界面，通过在通知区域中，打开 Azure 图标的快捷菜单，然后选择**显示计算模拟器 UI**。

    UI 的左的窗格显示了当前部署到计算仿真程序以及每个服务正在运行的角色实例的服务。 可以选择服务或角色，以在右窗格中显示生命周期、 日志记录和诊断信息。 如果将焦点置于包括窗口的上边距中，它将展开以填写右侧窗格。

3. 通过应用程序通过选择上的命令的步骤**调试**菜单，然后在代码中设置断点。 单步执行调试器中的应用程序，窗格会更新该应用程序的当前状态。 当你停止调试时，请删除应用程序部署。 如果你的应用程序包含 web 角色，并且已设置为启动 web 浏览器将启动操作属性，Visual Studio 在浏览器中启动 web 应用程序。 如果更改服务配置中的角色实例数，必须停止云服务，然后重新启动调试，以便可以调试这些新角色实例。

    **注意：** 时停止运行或调试服务时，不会停止本地计算仿真程序和存储仿真程序。 您必须显式将其停止从通知区域。

## <a name="debug-a-cloud-service-in-azure"></a>在 Azure 中调试云服务

若要调试在远程计算机的云服务，您必须启用该功能显式时部署你的云服务，以便所需运行角色实例的虚拟机上安装服务 (例如 msvsmon.exe)。 如果未启用远程调试的发布服务时，您必须重新发布该服务启用远程调试。

如果启用远程调试云服务，它不会导致性能下降或产生额外费用。 不要使用远程调试的生产服务，因为使用该服务的客户端可能会产生负面影响。

> [!NOTE]
> 当从 Visual Studio 的云服务发布时，可以启用**IntelliTrace**该服务中的.NET Framework 4 或.NET Framework 4.5 为目标的角色。 通过使用**IntelliTrace**，可以检查过去发生在角色实例中的事件并重现当时的上下文。 请参阅[调试已发布的云服务使用 IntelliTrace 和 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=623016)并[使用 IntelliTrace](https://msdn.microsoft.com/library/dd264915.aspx)。

### <a name="to-enable-remote-debugging-for-a-cloud-service"></a>若要为云服务启用远程调试

1. 打开 Azure 项目的快捷菜单，然后选择**发布**。

2. 选择**过渡**环境并**调试**配置。

    这是仅供指导。 您可以选择在生产环境中运行你的测试环境。 但是，如果启用远程调试在生产环境可能产生负面影响的用户。 可以选择发布配置，但调试配置会使调试更加容易。

    ![选择调试配置](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746717.gif)

3. 按照一般步骤，但选择**为所有角色启用远程调试器**上的复选框**高级设置**选项卡。

    ![调试配置](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746718.gif)

### <a name="to-attach-the-debugger-to-a-cloud-service-in-azure"></a>若要将调试器附加到 Azure 中的云服务

1. 在服务器资源管理器，展开云服务的节点。

2. 打开你想要将附加，并选择的角色或角色实例的快捷菜单**附加调试器**。

    如果调试某个角色时，Visual Studio 调试器将附加到该角色的每个实例。 调试器将运行该代码行并符合该断点的任何条件的第一个角色实例在断点处中断。 如果调试某个实例，调试器附加到该实例并仅当该特定实例运行的代码行并符合该断点的条件时，才在断点处中断。

    ![附加调试器](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746719.gif)

3. 将调试器附加到实例后，像通常那样调试。 调试器自动附加到你的角色的相应主机进程。 根据角色是什么，调试器将附加到 w3wp.exe、 WaWorkerHost.exe 或 WaIISHost.exe。 若要确认调试器附加到进程，展开服务器资源管理器中的实例节点。 请参阅[Azure 角色体系结构](http://blogs.msdn.com/b/kwill/archive/2011/05/05/windows-azure-role-architecture.aspx)有关 Azure 进程的详细信息。

    ![选择代码类型对话框](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC718346.png)

4. 若要识别调试器附加到进程，打开进程对话框的中，通过在菜单栏中选择调试、 Windows、 进程上。 (键盘： Ctrl + Alt + Z)若要分离特定的进程，打开其快捷菜单，并选择**分离进程**。 或者，在服务器资源管理器中找到实例节点，找到该进程中，打开其快捷菜单，并选择**分离进程**。

    ![调试进程](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC690787.gif)

> [!WARNING]
> 避免长时间停止在断点时远程调试。 Azure 将处理过程已停止的时间超过几分钟时间为无响应，会停止向该实例发送流量。 如果您停止的时间太长，msvsmon.exe 将与进程分离。

若要将调试器与分离所有进程实例或角色中，打开角色或实例，它进行调试，然后选择快捷菜单**都分离调试器**。

## <a name="limitations-of-remote-debugging-in-azure"></a>在 Azure 中的远程调试的限制

从 Azure SDK 2.3 开始，远程调试存在以下限制：

* 启用远程调试，则无法发布云服务在其中的任一角色包含 25 个以上的实例。
* 调试器使用端口 30400 至 30424、 端口 31400 至 31424 以及端口 32400 至 32424。 如果你尝试使用其中的任一端口，您将无法发布你的服务，和以下错误消息之一将 Azure 中显示活动日志：

  * 验证.cscfg 文件根据.csdef 文件时出错。
    保留的端口范围 range 终结点 Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector 的角色 role 与已定义的端口或范围重叠。
  * Allocation failed. 请稍后重试，尝试减小 VM 大小或角色实例数减少或尝试部署到不同的区域。

## <a name="debugging-azure-virtual-machines"></a>调试 Azure 虚拟机

您可以调试在 Visual Studio 中使用服务器资源管理器在 Azure 虚拟机运行的程序。 启用 Azure 虚拟机上的远程调试时，Azure 会在虚拟机上安装远程调试扩展。 然后，可以将附加到虚拟机上的进程，并像通常一样进行调试。

> [!NOTE]
> 通过 Azure resource manager 堆栈创建的虚拟机可以在 Visual Studio 2015 中使用云资源管理器进行远程调试。 有关详细信息，请参阅[使用云资源管理器管理 Azure 资源](http://go.microsoft.com/fwlink/?LinkId=623031)。

### <a name="to-debug-an-azure-virtual-machine"></a>若要调试 Azure 虚拟机

1. 在服务器资源管理器，展开虚拟机节点并选择你想要调试的虚拟机的节点。

2. 打开上下文菜单，然后选择**启用调试**。 当系统询问您是否确定如果你想要选择虚拟机上启用调试时**是**。

    Azure 虚拟机，若要启用调试上安装远程调试扩展。

    ![虚拟机启用调试命令](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746720.png)

    ![Azure 活动日志](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746721.png)

3. 完成安装远程调试扩展后，打开虚拟机的上下文菜单并选择**附加调试器...**

    Azure 虚拟机上获取进程的列表，并在附加到进程对话框中显示它们。

    ![附加调试器命令](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746722.png)

4. 在中**附加到进程**对话框中，选择**选择**来限制结果列表显示仅想要调试的代码类型。 您可以调试 32 位或 64 位托管的代码、 本机代码，或两者。

    ![选择代码类型对话框](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC718346.png)

5. 选择你想要在虚拟机上进行调试，然后选择的进程**附加**。 例如，可以选择 w3wp.exe 进程，如果你想要调试虚拟机上的 web 应用。 请参阅[调试一个或在 Visual Studio 中的多个进程](https://msdn.microsoft.com/library/jj919165.aspx)并[Azure 角色体系结构](http://blogs.msdn.com/b/kwill/archive/2011/05/05/windows-azure-role-architecture.aspx)有关详细信息。

## <a name="create-a-web-project-and-a-virtual-machine-for-debugging"></a>创建 web 项目和用于调试的虚拟机

发布 Azure 项目之前, 你可能会发现它可以支持调试和测试方案，并可以在其中安装测试和监视程序的受控环境中对其进行测试。 若要运行此类测试的一种方法是远程调试您的虚拟机上的应用程序。

Visual Studio ASP.NET 项目提供了一个选项以创建用于应用程序测试的方便的虚拟机。 虚拟机包含通常所需的终结点，例如 PowerShell、 远程桌面和 WebDeploy。

### <a name="to-create-a-web-project-and-a-virtual-machine-for-debugging"></a>若要创建的 web 项目和用于调试的虚拟机

1. 在 Visual Studio 中，创建一个新的 ASP.NET Web 应用程序。

2. 在新建 ASP.NET 项目对话框中，在 Azure 的部分中，选择**虚拟机**下拉列表框中。 将保留**创建远程资源**复选框处于选中状态。 选择**确定**以继续。

    **在 Azure 上创建虚拟机**对话框随即出现。

    ![创建 ASP.NET web 项目对话框](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746723.png)

    **注意：** 系统将要求你登录到你的 Azure 帐户如果尚未登录。

3. 选择虚拟机的各种设置，然后选择**确定**。 请参阅[虚拟机](http://go.microsoft.com/fwlink/?LinkId=623033)有关详细信息。

    输入 DNS 名称的名称将是虚拟机的名称。

    ![在 Azure 对话框上创建虚拟机](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746724.png)

    Azure 创建虚拟机，然后设置并配置终结点，例如远程桌面和 Web 部署

4. 虚拟机完全配置好后，在服务器资源管理器中选择虚拟机的节点。

5. 打开上下文菜单，然后选择**启用调试**。 当系统询问您是否确定如果你想要选择虚拟机上启用调试时**是**。

    Azure 会远程调试扩展安装到虚拟机，若要启用调试。

    ![虚拟机启用调试命令](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746720.png)

    ![Azure 活动日志](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746721.png)

6. 发布你的项目中所述[如何： 部署 Web 项目使用一键式发布 Visual Studio 中](https://msdn.microsoft.com/library/dd465337.aspx)。 因为你想要在虚拟机上进行调试**设置**页**发布 Web**向导中，选择**调试**作为配置。 这可确保在调试时提供了代码符号。

    ![发布设置](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC718349.png)

7. 在中**文件发布选项**，选择**删除目标处的其他文件**如果项目已经部署了较早的时间。

8. 发布项目，在服务器资源管理器中的虚拟机的上下文菜单上后选择**附加调试器...**

    Azure 虚拟机上获取进程的列表，并在附加到进程对话框中显示它们。

    ![附加调试器命令](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC746722.png)

9. 在中**附加到进程**对话框中，选择**选择**来限制结果列表显示仅想要调试的代码类型。 您可以调试 32 位或 64 位托管的代码、 本机代码，或两者。

    ![选择代码类型对话框](./media/vs-azure-tools-debug-cloud-services-virtual-machines/IC718346.png)

10. 选择你想要在虚拟机上进行调试，然后选择的进程**附加**。 例如，可以选择 w3wp.exe 进程，如果你想要调试虚拟机上的 web 应用。 请参阅[调试一个或多个进程在 Visual Studio 中](https://msdn.microsoft.com/library/jj919165.aspx)有关详细信息。

## <a name="next-steps"></a>后续步骤

* 使用**Intellitrace**从发布服务器中收集调用和事件的日志。 请参阅[调试已发布的云服务使用 IntelliTrace 和 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=623016)。

* 使用**Azure 诊断**角色内运行的代码记录的详细的信息，是否在开发环境中或在 Azure 中运行的角色。 请参阅[使用 Azure 诊断收集日志记录数据](http://go.microsoft.com/fwlink/p/?LinkId=400450)。
