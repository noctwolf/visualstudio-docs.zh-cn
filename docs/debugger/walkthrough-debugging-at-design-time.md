---
title: 在设计时的 Visual Studio 调试 |Microsoft 文档
ms.custom: ''
ms.date: 02/21/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c569ba018cfaa65cf2fec3edcf0676ef374db225
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="debug-at-design-time-in-visual-studio"></a>在 Visual Studio 中的设计时调试

在某些情况下，你可能想要调试代码中的在设计时运行该应用程序，而不是时间。 你可以执行此使用**即时**窗口。 如果你想要调试与其他代码，如数据绑定代码进行交互的 XAML 代码可以使用**调试** > **附加到进程**执行此操作。
  
### <a name="debug-at-design-time-using-the-immediate-window"></a>在使用即时窗口的设计时调试  

你可以使用 Visual Studio**即时**窗口在你的应用程序未运行时执行函数或子例程。 如果函数或子例程包含断点，Visual Studio 会在合适的点处中断执行。 随后即可使用调试器窗口检查程序状态。 此功能称为在设计时调试。  

下面的示例是在 Visual Basic 中，但**即时**窗口也支持在 C# 和 c + + 应用程序。
  
1.  将以下代码粘贴到 Visual Basic 控制台应用程序：  
  
    ```vb  
    Module Module1  
  
        Sub Main()  
            MySub()  
        End Sub  
  
        Function MyFunction() As Decimal  
            Static i As Integer  
            i = i + 1  
            Dim s As String  
  
            s = "Add Breakpoint here"  
            Return 4  
        End Function  
  
        Sub MySub()  
            MyFunction()  
        End Sub  
    End Module  
    ```  
  
2.  在读取时，行上设置断点`s="Add BreakPoint Here"`。  
  
3.  打开**即时**窗口 (**调试** > **Windows** > **即时**) 并键入以下内容中的窗口： `?MyFunction<enter>`  
  
4.  验证该断点被命中，以及调用堆栈准确。  
  
5.  上**调试**菜单上，单击**继续**，然后验证是否仍然处于设计模式。  
  
6.  键入以下内容中的**即时**窗口： `?MyFunction<enter>`  
  
7.  键入以下内容中的**即时**窗口： `?MySub<enter>`  
  
8.  验证你命中了断点，并检查的静态变量的值`i`中**局部变量**窗口。 它应具有的值为 3。  
  
9. 验证调用堆栈准确。  
  
10. 上**调试**菜单上，单击**继续**，然后验证是否仍然处于设计模式。  

## <a name="debug-at-design-time-from-the-xaml-designer"></a>从 XAML 设计器的设计时调试

它可以帮助调试中某些声明性数据绑定方案的 XAML 设计器从代码隐藏。

1. 在项目中，添加一个新的 XAML 页，如*temp.xaml*。 将新的 XAML 页留空。 

1. 编译你的解决方案。

1. 打开*temp.xaml*，这会将加载设计器 (*UwpSurface.exe*在 UWP 应用中，或*XDesProc.exe*) 以便你可以将附加到它在后来的步骤。 

1. 打开 Visual Studio 的新实例。 在新的实例中，打开**附加到进程**对话框 (**调试** > **附加到进程**)，请设置**将附加到**字段到正确的代码类型，如**托管代码 (CoreCLR)**或基于你的.NET 版本的正确的代码类型。 从列表中选择正确的设计器进程，然后选择**附加**。

    适用于 UWP 面向的项目生成 16299 或更高版本，设计器的进程是*UwpSurface.exe*。 对于 WPF 或 UWP 的版本低于 16299，设计器的进程是*XDesProc.exe*。

1. 在附加到进程时，切换到你的项目，打开你想要调试的后台代码并设置断点。

1. 最后，打开包含 XAML 代码，其中包括数据绑定的页。

    例如，你无法设置断点的类型转换器代码中为以下 XAML，这是将一个 TextBlock 绑定在设计时。

    ```xaml
    <TextBlock Text="{Binding title, ConverterParameter=lower, Converter={StaticResource StringFormatConverter}, Mode=TwoWay}"  />
    ```
   加载页时命中断点。
  
## <a name="see-also"></a>请参阅  
 [调试器安全](../debugger/debugger-security.md)   
 [调试器基础知识](../debugger/debugger-basics.md)
