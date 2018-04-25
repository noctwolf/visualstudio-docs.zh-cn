---
title: 工具箱，“组件”选项卡 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Toolbox, Components tab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 29fd00d6fdf6f973149f57a78eb1145274689a2b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="toolbox-components-tab"></a>工具箱，“组件”选项卡

显示可以添加到 Visual Basic 和 C# 设计器的组件。 除 Visual Studio 附带的 .NET Framework 组件（如 <xref:System.Messaging.MessageQueue> 和 <xref:System.Diagnostics.EventLog> 组件）外，还可向此选项卡添加自己的组件或第三方组件。
  
 若要显示此选项卡，请从“视图”菜单中选择“工具箱”。 在“工具箱”中，选择“组件”选项卡。  
  
 **BackgroundWorker**  
 创建可在单独的专用线程上运行操作的 `System.ComponentModel.BackgroundWorker` 组件实例。  
  
 **DirectoryEntry**  
 创建 <xref:System.DirectoryServices.DirectoryEntry> 组件实例，它封装 Active Directory 层次结构中的节点或对象，可用于与 Active Directory 服务提供商交互。  
  
 **DirectorySearcher**  
 创建 <xref:System.DirectoryServices.DirectorySearcher> 组件实例，该实例可用于对 Active Directory 执行查询。  
  
 **ErrorProvider**  
 创建 `System.Windows.Forms.ErrorProvider` 组件实例，该实例向最终用户指示窗体上的控件具有与其关联的错误。  
  
 **EventLog**  
 创建 <xref:System.Diagnostics.EventLog> 组件实例，该实例可用于与系统和自定义事件日志进行交互，包括将事件写入日志和读取日志数据。
  
 **FileSystemWatcher**  
 创建 <xref:System.IO.FileSystemWatcher> 组件实例，该实例可用于监视你有权访问的任何目录或文件的更改。
  
 **HelpProvider**  
 创建为控件提供弹出帮助或联机帮助的 `System.Windows.Forms.HelpProvider` 组件实例。  
  
 **ImageList**  
 创建 `System.Windows.Forms.ImageList` 组件实例，该实例提供管理 `System.Drawing.Image` 对象集合的方法。  
  
 **MessageQueue**  
 创建 <xref:System.Messaging.MessageQueue> 组件实例，该实例可用于与消息队列进行交互，包括从队列读取消息和向队列写入消息、处理事务以及执行队列管理任务。

 **PerformanceCounter**  
 创建 <xref:System.Diagnostics.PerformanceCounter> 组件实例，该实例可用于与 Windows 性能计数器进行交互，包括创建新类别和实例、从计数器读取值以及对计数器数据执行计算。
  
 **Process**  
 创建 <xref:System.Diagnostics.Process> 组件实例，可用于停止、启动和操作与系统上的进程关联的数据。
  
 **SerialPort**  
 创建 `System.IO.Ports.SerialPort` 组件实例，该实例提供同步和事件驱动 I/O、提供对插针和中断状态的访问以及对串行驱动程序属性的访问。  
  
 **ServiceController**  
 创建 <xref:System.ServiceProcess.ServiceController> 组件实例，该实例可用于操作现有服务，包括启动和停止服务及向其发送命令。
  
 **计时器**  
 创建 <xref:System.Windows.Forms.Timer> 组件实例，该实例可用于向基于 Windows 的应用程序添加基于时间的功能。 有关详细信息，请参阅 [Timer 组件](/dotnet/framework/winforms/controls/timer-component-windows-forms)。  
  
> [!NOTE]
>  此外，还有一个基于系统的 <xref:System.Timers.Timer>，可将其添加到“工具箱”。此 <xref:System.Timers.Timer> 针对服务器应用程序进行了优化，Windows 窗体 <xref:System.Windows.Forms.Timer> 最适合在 Windows 窗体上使用。  
  
## <a name="see-also"></a>请参阅

[使用组件编程](http://msdn.microsoft.com/Library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)  
[组件编程演练](http://msdn.microsoft.com/Library/373cacf7-479e-4b05-991c-5cb18824e913)  
[工具箱](../../ide/reference/toolbox.md)