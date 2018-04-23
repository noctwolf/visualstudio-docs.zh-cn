---
title: 如何： 显示 WPF 跟踪信息 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- WPF, debugging
- debugging, WPF
ms.assetid: be3c6859-06e1-459e-9fd0-46375b5f55ef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 99fc861c627a094f9f5e4e67a6b034ecdd407688
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-display-wpf-trace-information"></a>如何：显示 WPF 跟踪信息
[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 可以接收来自 WPF 应用程序的调试跟踪信息以及显示在该信息**输出**窗口。 若要显示调试跟踪信息，必须启用 WPF 跟踪。  
  
 可以在 App.Config 文件中启用 WPF 跟踪，或通过使用 <xref:System.Diagnostics.PresentationTraceSources> 类以编程方式启用 WPF 跟踪。 若要启用 WPF 跟踪更简单的方法是使用**选项**窗口。 不支持针对 Web 应用程序的 WPF 跟踪。  
  
### <a name="to-enable-or-customize-wpf-trace-information"></a>启用或自定义 WPF 跟踪信息  
  
1.  在“工具”菜单上选择“选项”。  
  
2.  在**选项**对话框中，在左侧框中，打开**调试**节点。  
  
3.  下**调试**，单击**输出窗口**。  
  
4.  下**常规输出设置**，选择**所有调试输出**。  
  
5.  在右侧框中，查找**WPF 跟踪设置**。  
  
6.  打开**WPF 跟踪设置**节点。  
  
7.  下**WPF 跟踪设置**，单击你想要启用的设置的类别 (例如，**数据绑定**)。  
  
     下拉列表控件中将出现设置列下一步**数据绑定**或您单击的任何类别。  
  
8.  单击下拉列表并选择你想要查看的跟踪信息的类型：**所有**，**严重**，**错误**，**警告**， **信息**，**详细**，或**ActivityTracing**。  
  
     **关键**启用仅关键事件的跟踪。  
  
     **错误**启用严重和错误事件的跟踪。  
  
     **警告**启用跟踪的严重、 错误和警告事件。  
  
     **信息**启用严重、 错误、 警告和信息事件的跟踪。  
  
     **详细**启用严重、 错误、 警告、 信息和详细的事件的跟踪。  
  
     **ActivityTracing**启用停止、 开始、 挂起、 传输和恢复事件的跟踪。  
  
     有关这些跟踪信息级别的含义的更多信息，请参见 <xref:System.Diagnostics.SourceLevels>。  
  
9. 单击 **“确定”**。  
  
### <a name="to-disable-wpf-trace-information"></a>禁用 WPF 跟踪信息  
  
1.  在“工具”菜单上选择“选项”。  
  
2.  在**选项**对话框中，在左侧框中，打开**调试**节点。  
  
3.  下**调试**，单击**输出窗口**。  
  
4.  在右侧框中，查找**WPF 跟踪设置**。  
  
5.  打开**WPF 跟踪设置**节点。  
  
6.  下**WPF 跟踪设置**，单击你想要启用的设置的类别 (例如，**数据绑定**)。  
  
     下拉列表控件中将出现设置列下一步**数据绑定**或您单击的任何类别。  
  
7.  单击下拉列表并选择**关闭**。  
  
8.  单击 **“确定”**。  
  
## <a name="see-also"></a>请参阅  
 [调试 WPF](../debugger/debugging-wpf.md)