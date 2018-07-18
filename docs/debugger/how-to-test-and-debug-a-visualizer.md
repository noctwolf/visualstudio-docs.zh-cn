---
title: 如何： 测试和调试可视化工具 |Microsoft 文档
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
- visualizers, testing
- visualizers, debugging
- debugging [Visual Studio], visualizers
ms.assetid: 5cc12ce8-c819-48e4-b487-98d403001b28
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 860d6bd5f89ff85f3abf75f1beceb62b6b860d54
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31476132"
---
# <a name="how-to-test-and-debug-a-visualizer"></a>如何：测试和调试可视化工具
编写完可视化工具后，需要对其进行调试和测试。  
  
 测试可视化工具的一种方法是将它安装在 Visual Studio 中并从调试器窗口进行调用。 (请参阅[如何： 安装可视化工具](../debugger/how-to-install-a-visualizer.md)。)如果采用这种方法，则需要使用另一个 Visual Studio 实例附加和调试正在第一个调试器实例中运行的可视化工具。  
  
 一种更简单的调试可视化工具的方法，是从测试驱动程序运行可视化工具。 可视化工具 Api 使其可以轻松地创建此类驱动程序，称为*可视化工具开发宿主*。  
  
### <a name="to-create-a-visualizer-development-host"></a>创建可视化工具开发宿主  
  
1.  在调试器端类中，包含一个创建 <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerDevelopmentHost> 对象并调用其 show 方法的静态方法：  
  
    ```  
    public static void TestShowVisualizer(object objectToVisualize)  
    {  
       VisualizerDevelopmentHost myHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));  
       myHost.ShowVisualizer();  
    }  
    ```  
  
     用于构造宿主的参数是数据对象（将显示在可视化工具 (`objectToVisualize`) 中）和调试器端类的类型。  
  
2.  添加下面的语句以调用 `TestShowVisualizer`。 如果可视化工具是在类库中创建的，则需要创建调用该类库的可执行文件，并将此语句放置到可执行文件中：  
  
    ```  
    DebuggerSide.TestShowVisualizer(myString);  
    ```  
  
     有关更完整示例，请参阅[演练： 在 C# 中编写可视化工具](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)。  
  
## <a name="see-also"></a>请参阅  
 [演练： 用 C# 编写可视化工具](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)   
 [如何： 安装可视化工具](../debugger/how-to-install-a-visualizer.md)   
 [创建自定义可视化工具](../debugger/create-custom-visualizers-of-data.md)