---
title: 可视化工具体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 6aad395f-7170-4d9e-b2b8-a5faf453380e
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 086877250d513d8f8b033c9085bd1ff80ce3fa87
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479433"
---
# <a name="visualizer-architecture"></a>可视化工具体系结构
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[可视化工具体系结构](https://docs.microsoft.com/visualstudio/debugger/visualizer-architecture)。  
  
调试器可视化工具的结构由两部分组成：  
  
-   *调试器端*程序在 Visual Studio 调试器中运行。 调试器端代码创建并显示可视化工具的用户界面。  
  
-   *调试对象端*在 Visual Studio 正在调试的进程中运行 (*调试对象*)。  
  
 可视化工具是使调试器能够显示一个调试器组件 (*可视化*) 有意义且易于理解的窗体中的数据对象的内容。 某些可视化工具还支持数据对象编辑。 通过编写自定义可视化工具，可以扩展调试器的功能，使其能够处理你自己的自定义数据类型。  
  
 要可视化的数据对象位于要调试的进程内 (*调试对象*过程)。 用于显示数据的用户界面在 Visual Studio 调试器进程内创建：  
  
|调试器进程|调试对象进程|  
|----------------------|----------------------|  
|调试器用户界面（数据提示、监视窗口、快速监视）|要可视化的数据对象|  
  
 若要在调试器界面中可视化数据对象，则需要一些代码，以实现两个进程间的通信。 由此可见，可视化工具体系结构由两个部分组成：*调试器端*代码和*调试对象端*代码。  
  
 调试器端代码用于创建其自身用户界面，该界面可从调试器界面调用，例如数据提示、监视窗口或快速监视。 可以使用 <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer> 类和 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService> 界面来创建可视化工具界面。 与所有的可视化工具 API 一样，DialogDebuggerVisualizer 和 IDialogVisualizerService 可在 <xref:Microsoft.VisualStudio.DebuggerVisualizers> 命名空间中找到。  
  
|调试器端|调试对象端|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer 类<br /><br /> IDialogVisualizerService 界面|数据对象|  
  
 用户界面可从位于调试器端的对象提供程序获得要可视化的数据：  
  
|调试器端|调试对象端|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer 类<br /><br /> IDialogVisualizerService 界面|数据对象|  
|对象提供程序（实现 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider>）||  
  
 调试对象端有一个对应的对象，称作对象源：  
  
|调试器端|调试对象端|  
|-------------------|-------------------|  
|DialogDebuggerVisualizer 类<br /><br /> IDialogVisualizerService 界面|数据对象|  
|对象提供程序（实现 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider>）|对象源（从 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource> 派生）|  
  
 对象提供程序向可视化工具用户界面提供要可视化的对象数据。 这些数据对象是对象提供程序从对象源获得的。 对象提供程序和对象源提供 API，以便在调试器端和调试对象端之间传输对象数据。  
  
 每个可视化工具都必须获得要可视化的数据对象。 下表给出了对象提供程序和对象源用于此目的的相应 API：  
  
|对象提供程序|对象源|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A><br /><br /> - 或 -<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A>|  
  
 注意，对象提供程序既可使用 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A>，也可使用 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A>。 其个任何一个 API 均会针对对象源调用 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A>。 调用<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.GetData%2A?displayProperty=fullName>填写 [System.IO.Stream] (<!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->)，它表示要可视化的对象的序列化的形式。  
  
 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A?displayProperty=fullName> 将数据重新反序列化为对象形式，使你可以在使用 <xref:Microsoft.VisualStudio.DebuggerVisualizers.DialogDebuggerVisualizer> 创建的 UI 中显示该对象。 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName> 填入原始 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  --> 形式的数据，你必须自己反序列化这些数据。 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A?displayProperty=fullName> 的工作方式是调用 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName> 来获得序列化的 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->，然后再对数据进行反序列化处理。 如果 .NET 无法序列化该对象，而需要自定义序列化时，请使用 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A?displayProperty=fullName>。 在这种情况下，你还必须重写 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.Serialize%2A?displayProperty=fullName> 方法。  
  
 如果要创建只读可视化工具，则与 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetData%2A> 或 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.GetObject%2A> 的单向通信就可满足要求。 如果要创建支持数据对象编辑的可视化工具，还必须进行其他操作。 你还必须能够将数据对象从对象提供程序返回给对象源。 下表给出了对象提供程序和对象源用于此目的的 API：  
  
|对象提供程序|对象源|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A><br /><br /> - 或 -<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.CreateReplacementObject%2A>|  
  
 再次提请注意，对象提供程序可使用的 API 有两个。 数据总是以 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  --> 的形式从对象提供程序发送到对象源，但是，<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A> 要求你自己将对象序列化为 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->。  
  
 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceObject%2A> 获取你提供的对象，将其序列化为 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  -->，然后调用 <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.ReplaceData%2A> 将 <!-- TODO: review code entity reference <xref:assetId:///System.IO.Stream?qualifyHint=False&amp;autoUpgrade=True>  --> 发送到 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.CreateReplacementObject%2A>。  
  
 使用其中任意一个 Replace 方法将在调试对象中创建一个新数据对象，然后用该对象代替要可视化的对象。 如果你要更改原始对象的内容但不替换它，请使用下表中给出的一个 Transfer 方法。 这些 API 可同时进行双向数据传输，而无需替换要可视化的对象：  
  
|对象提供程序|对象源|  
|---------------------|-------------------|  
|<xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.TransferData%2A><br /><br /> - 或 -<br /><br /> <xref:Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider.TransferObject%2A>|<xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerObjectSource.TransferData%2A>|  
  
## <a name="see-also"></a>请参阅  
 [如何： 编写可视化工具](../debugger/how-to-write-a-visualizer.md)   
 [演练： 用 C# 编写可视化工具](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)   
 [演练： 用 Visual Basic 编写可视化工具](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)   
 [演练： 用 Visual Basic 编写可视化工具](../debugger/walkthrough-writing-a-visualizer-in-visual-basic.md)   
 [可视化工具安全注意事项](../debugger/visualizer-security-considerations.md)



