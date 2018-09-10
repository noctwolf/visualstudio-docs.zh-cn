---
title: 项目用于 C# 调试配置的设置 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debug configurations, C#
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debugging [C#], debugger settings
ms.assetid: e30ca810-66e9-4d6e-9cf6-9f285cd0b100
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: c5bd49d550cb03e8234c8740ea8c0f605ed721c2
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283257"
---
# <a name="project-settings-for--c-debug-configurations"></a>C# 调试配置的项目设置
可以更改 C# 调试配置中的项目设置**属性页**窗口中，如中所述[调试和发布配置](../debugger/how-to-set-debug-and-release-configurations.md)。 下表显示了在何处可以找到中与调试器相关的设置**属性页**窗口。  
  
> [!WARNING]
>  本主题不适用于 UWP 应用。 请参阅[启动调试会话 (VB、 C#、 c + + 和 XAML）](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
##  <a name="BKMK_Debug_tab"></a> 调试选项卡  
  
|**设置**|**说明**|  
|-----------------|---------------------|  
|**配置**|设置编译应用程序的模式。 在其中进行选择**活动 （调试）**，**调试**，**版本**，**所有配置**。|  
|**启动操作**|这组控件指定在从“调试”菜单中选择“启动”时将发生的操作。<br /><br /> -   **启动项目**是默认值，用于启动启动项目以便进行调试。 有关详细信息，请参阅[选择启动项目](/previous-versions/visualstudio/visual-studio-2010/0s590bew(v=vs.100))。<br />-   **启动外部程序**使您能够启动并附加到不是程序的一部分[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]项目。 有关详细信息，请参阅[附加到正在运行的程序](/previous-versions/visualstudio/visual-studio-2010/c6wf8e4z(v=vs.100))。<br />-   **启动浏览器于 URL**使你能够调试 Web 应用程序。|  
|**命令行参数**|指定要调试的程序的命令行自变量。 该命令名是在“启动外部程序”中指定的程序名。 如果“启动操作”设置为“启动 URL”，则不能指定命令行自变量。|  
|**工作目录**|指定被调试的程序的工作目录。 在 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 中，工作目录是启动应用程序的目录，默认情况下为 \bin\debug。|  
|**使用远程计算机**|出于调试目的的远程计算机运行该应用程序的名称或[Msvsmon 服务器名称](../debugger/remote-debugging.md)。 该 EXE 文件在远程计算机上的位置是由“配置属性”文件夹“生成”类别中的“输出路径”属性指定的。 此位置必须是远程计算机上的共享目录。|
|**启用非托管代码调试**|使你能够从托管应用程序中调试对本机（非托管）Win32 代码的调用。|  
|**启用 SQL Server 调试**|允许对 SQL Server 数据库对象进行调试。|  
  
##  <a name="BKMK_Build_tab"></a> 生成选项卡  
  
|设置|描述|  
|-------------|-----------------|  
|**条件编译符号：**|此处定义 DEBUG 和 TRACE 常数。<br /><br /> 这些常数启用的条件编译[Debug 类](/dotnet/api/system.diagnostics.debug)并[Trace 类](/dotnet/api/system.diagnostics.trace)。 使用这些定义的常量，调试和 Trace 类方法生成的输出[输出窗口](../ide/reference/output-window.md)。 如果没有这两个常数，则 Debug 和 Trace 类方法将不会被编译，并且不生成任何输出。<br /><br /> 调试通常是程序的调试版本中定义和发布版本中未定义。<br />的通常在调试和发布版本中定义跟踪。|  
|**优化代码**|除非发现仅出现在优化代码中的 bug，否则应在调试版本中将此设置关闭。 优化代码更难调试，因为指令与源窗口中的语句并不是直接对应的。|  
|**输出路径：**|通常设置为 bin\Debug 以用于调试。|

> [!NOTE]
> 有关详细信息中找到的调试选项**高级**按钮，请参阅[高级生成设置对话框 (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md)。 符号 (.pdb) 文件的可移植格式是为.NET Core 的最新的跨平台格式。 
  
## <a name="see-also"></a>请参阅  
 [调试器设置和准备](../debugger/debugger-settings-and-preparation.md)