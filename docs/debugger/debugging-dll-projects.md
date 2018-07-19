---
title: 调试 DLL 项目 |Microsoft Docs
ms.custom: ''
ms.date: 05/23/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging DLLs
- templates, debugging DLLs
- DLLs, debugging
- debugging [Visual Studio], DLLs
ms.assetid: 433cab30-d191-460b-96f7-90d2530ca243
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d5118aafae296d839ad182d51b996da11a6bc556
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057393"
---
# <a name="debugging-dll-projects-from-visual-studio"></a>从 Visual Studio 的调试 DLL 项目
下面的 Visual Studio 模板创建 Dll:  
  
-   （C++、C# 和 Visual Basic）：类库   

-   （c + +）： Win32 控制台 DLL 项目
  
     有关更多信息，请参见 [MFC Debugging Techniques](../debugger/mfc-debugging-techniques.md)。

-   （C++、C# 和 Visual Basic）：Windows 窗体控件库
  
     调试 Windows 窗体控件库是类似于调试类库项目。 大多数情况下将从另一个项目中调用 Windows 控件。 调试调用项目时，可单步执行 Windows 控件的代码，并设置断点，然后执行其他调试操作。 有关详细信息，请参阅 [Windows 窗体控件](/dotnet/framework/winforms/controls/index)。  

  
##  <a name="vxtskdebuggingdllprojectsbuildingadebugversion"></a> Building a debug version  
 无论如何启动调试，都请首先确保生成 DLL 的调试版本，并确保该调试版本位于应用程序应该能够找到它的位置。 这似乎很明显，但如果忘记这一步骤，应用程序可能会找到并加载 DLL 的其他版本。 然后程序将继续运行，尽管您会奇怪为什么断点从未被命中。 调试时，可以通过打开调试器的 **“模块”** 窗口来检查程序已加载的 DLL。 **“模块”** 窗口列出了所调试进程中加载的每个 DLL 或 EXE。 有关详细信息，请参阅 [How to: Use the Modules Window](../debugger/how-to-use-the-modules-window.md)。  
 为了使调试器附加到用 C++ 编写的代码，该代码必须发出 `DebuggableAttribute`。 可通过链接 [/ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute) 链接器选项将它自动添加到代码中。  
  
##  <a name="vxtskdebuggingdllprojectsmixedmodedebugging"></a> Mixed-Mode debugging  
 调用 DLL 的调用应用程序可以用托管代码编写，也可以用本机代码编写。 如果托管 DLL 由本机代码调用，并且您需要调试两者，则必须同时启用托管调试器和本机调试器。 可以选择在此**\<项目 > 属性页**对话框或窗口。 具体如何检查取决于是从 DLL 项目中启动调试，还是从调用应用程序项目中启动调试。 有关更多信息，请参见 [How to: Debug in Mixed Mode](../debugger/how-to-debug-in-mixed-mode.md)。  
  
##  <a name="vxtskdebuggingdllprojectschangingdefaultconfigurations"></a> Changing default configurations  
 用项目模板创建控制台应用程序项目时， [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 将自动为调试和发布配置创建所需的设置。 必要时，可更改这些设置。 有关详细信息，请参阅[c + + 调试配置的项目设置](../debugger/project-settings-for-a-cpp-debug-configuration.md)， [C# 调试配置的项目设置](../debugger/project-settings-for-csharp-debug-configurations.md)， [Visual Basic 调试配置的项目设置](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)，并[如何： 设置调试和发布配置](../debugger/how-to-set-debug-and-release-configurations.md)。  
  
##  <a name="vxtskdebuggingdllprojectswaystodebugthedll"></a> Ways to debug the DLL  
 本节的每个项目都创建一个 DLL。 您无法直接运行 DLL，它必须由应用程序（通常为 EXE）调用。 有关详细信息，请参阅 [Creating and Managing Visual C++ Projects](/cpp/ide/creating-and-managing-visual-cpp-projects)。 调用应用程序可能满足下列任一条件：  
  
-   内置在同一 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 解决方案中包含类库的另一个项目中的应用程序。  
  
-   已经部署到测试或生产计算机上的现有应用程序。  
  
-   位于 Web 上并通过 URL 访问。  
  
-   包含嵌入了 DLL 的网页的 Web 应用程序。  
  
###  <a name="vxtskdebuggingdllprojectsthecallingapplication"></a> Debugging the calling application  
若要调试 DLL，请从调试调用应用程序开始，通常是 EXE 或者 Web 应用程序。 调试方式有许多种。  
  
-   如果有调用应用程序的项目，则可以打开该项目并从 **“调试”** 菜单开始执行。 有关详细信息，请参阅[开始使用调试器](../debugger/getting-started-with-the-debugger.md)。  
  
-   如果调用应用程序是已经部署到测试或生产计算机上并已经运行的现有程序，则可以附加到该应用程序上。 如果 DLL 是由 Internet Explorer 承载的控件或网页上的控件，请使用此方法。 有关详细信息，请参阅 [How to: Attach to a Running Process](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)。  
  
-   您可以从 DLL 项目中调试。 有关详细信息，请参阅 [How to: Debug from a DLL Project](../debugger/how-to-debug-from-a-dll-project.md)。  
  
-   您可以从其进行调试[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)][即时窗口](#vxtskdebuggingdllprojectstheimmediatewindow)。 在这种情况下， **“即时”** 窗口充当应用程序的角色。  
  
在开始调试调用应用程序之前，通常希望在类库中设置一个断点。 有关详细信息，请参阅 [Using Breakpoints](../debugger/using-breakpoints.md)。 命中断点时，可以逐句通过代码，同时观察每行的操作，直到将问题隔离出来。 有关详细信息，请参阅[在调试器中导航代码](../debugger/navigating-through-code-with-the-debugger.md)。
  
###  <a name="vxtskdebuggingdllprojectstheimmediatewindow"></a> “即时”窗口  
 可以在没有调用应用程序的情况下计算 DLL 中的函数或方法。 可以进行设计时调试并使用 **“即时”** 窗口。 若要以这种方式进行调试，请在 DLL 项目打开时按照以下步骤操作：  
  
1.  打开调试器 **“即时”** 窗口。  
  
2.  若要测试类 `Test` 中名为 `Class1`的方法，请通过在“即时”窗口中键入以下 C# 代码来实例化类型为 `Class1` 的对象。 对语法进行以下适当更改后，此托管代码对 Visual Basic 和 C++ 有效：  
  
    ```cpp
    Class1 obj = new Class1();  
    ```  
  
     在 C# 中，所有名称必须是全限定名称。 而且，任何方法或变量都必须处在调试会话的当前范围和上下文中。  
  
3.  假设 `Test` 带有一个 `int` 参数，使用 `Test` “即时” **窗口计算** ：  
  
    ```cpp
    ?obj.Test(10)  
    ```  
  
     结果将打印在 **“即时”** 窗口中。  
  
4.  您可以继续调试 `Test` ，方法为在其中设置断点然后再次计算函数：  
  
    ```cpp
    ?obj.Test(10);  
    ```  
  
     断点将被命中，然后您将可以逐步调试 `Test`。 当执行离开 `Test`后，调试器将返回设计模式。

## <a name="vxtskdebuggingdllprojectsexternal"></a> 调试 c + + 项目的外部 DLL

如果正在调试你的项目外部 DLL，调试功能 （如单步执行代码） 将取决于[DLL 的调试配置](#vxtskdebuggingdllprojectsbuildingadebugversion)时其目标以及是否[.pdb 文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)和 DLL 的其他要求的文件都可用。

你的项目需要能够找到的 DLL，并用于调试的.pdb 文件。 可以创建自定义生成任务来复制这些文件复制到**\<项目文件夹 > \Debug**输出文件夹中，也可以手动将文件复制到输出文件夹中。

您可以轻松地设置属性页中的标头文件和 *.lib 文件的位置 (右键单击 c + + 项目，然后选择**查看属性**，然后选择**所有配置**) 而无需复制其输出文件夹：

- C/c + + 文件夹 （常规类别）-指定包含中的标头文件的文件夹**附加包含目录**字段。
- 链接器文件夹 （常规类别）-指定包含中的.lib 文件的文件夹**附加库目录**字段。 
- 链接器文件夹 （输入类别）-指定的完整路径和文件名的.lib 文件中**附加依赖项**字段。

正确配置时，您可以通过开始执行从调试**调试**菜单。

项目设置的详细信息，请参阅[属性页 （Visual c + +）](/cpp/ide/property-pages-visual-cpp)。
  
## <a name="see-also"></a>请参阅  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) （调试托管代码）  
 [Visual C++ 项目类型](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [C#、F#、和 Visual Basic 项目类型](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [C + + 调试配置的项目设置](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [C# 调试配置的项目设置](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Visual Basic 调试配置的项目设置](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [调试器安全](../debugger/debugger-security.md)
