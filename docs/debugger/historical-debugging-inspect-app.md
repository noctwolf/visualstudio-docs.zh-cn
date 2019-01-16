---
title: 检查使用历史调试对应用程序 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 629b5d93-39b2-430a-b8ba-d2a47fdf2584
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 998b94a13f3650446f9f791ffc29c7c863f9df89
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53968626"
---
# <a name="inspect-your-app-with-intellitrace-historical-debugging-in-visual-studio"></a>检查 IntelliTrace 历史调试在 Visual Studio 中使用对应用程序
可以使用[历史调试](../debugger/historical-debugging.md)向后移动和向前浏览应用程序的执行，以查看其状态。  
  
可以在 Visual Studio Enterprise 版（但不可在 Professional 或 Community 版）中使用 IntelliTrace。  
  
## <a name="navigate-your-code-with-historical-debugging"></a>导航使用历史调试代码  
 让我们从有 Bug 的简单程序开始。 在 C# 控制台应用程序中，添加以下代码：  
  
```csharp  
static void Main(string[] args)  
{  
    int testInt = 0;  
    int resultInt = AddAll(testInt);  
    Console.WriteLine(resultInt);  
}  
private static int AddAll(int j)  
{  
    for (int i = 0; i < 20; i++)  
    {  
        j = AddInt(j);  
    }  
    return j;  
}  
  
private static int AddInt(int add)  
{  
    if (add == 10)  
    {  
        return add += 25;  
    }  
    return ++add;  
}  
```  
  
 在调用 `AddAll()` 后，我们假设 `resultInt` 的期望值为 20（递增 `testInt` 20 次的结果）。 (我们还假定您不能看到该 bug 的`AddInt()`)。但结果实际上是 44。 如何在不逐句通过 `AddAll()` 10 次的情况下找到 Bug？ 可以使用历史调试更快速轻松地查找 bug。 操作方法如下：  
  
1.  在中**工具 > 选项 > IntelliTrace > 常规**，请确保启用了 IntelliTrace，然后选择**IntelliTrace 事件和调用信息**。 如果没有选择此选项，则将无法看到导航线（如下所述）。  
  
2.  在 `Console.WriteLine(resultInt);` 行上设置断点。  
  
3.  开始调试。 代码执行到断点。 在“局部变量”窗口中，可以看到 `resultInt` 的值是 44。  
  
4.  打开“诊断工具”窗口（“调试”>“显示诊断工具”）。 代码窗口应如下所示：  
  
     ![在断点处的代码窗口](../debugger/media/historicaldebuggingbreakpoint.png "HistoricalDebuggingBreakpoint")  
  
5.  你应该在左边距旁边看到一个双箭头，就在断点上方。 此区域称为导航线，它用于历史调试。 单击箭头。  
  
     在代码窗口中，应该看待前面的代码行 (`int resultInt = AddIterative(testInt);`) 变为粉红色。 在窗口上方，应该看到一条消息，告知你现在处于历史调试模式中。  
  
     代码窗口现在如下所示：  
  
     ![历史调试模式中的代码窗口](../debugger/media/historicaldebuggingback.png "HistoricalDebuggingBack")  
  
6.  现在，可以单步执行 `AddAll()` 方法（使用 F11，或导航线中的“单步执行”按钮）。 单步前进（使用 F10，或导航线中的“转到下一个调用”）。 粉红色的行现在变为 `j = AddInt(j);` 行。 在这种情况下，按 F10 不会单步执行到下一行代码。 相反，它将单步执行到下一个函数调用。 历史调试在调用之间进行导航，并跳过不包括函数调用的代码行。  
  
7.  现在单步执行到 `AddInt()` 方法。 应该立即看到此代码中的 Bug。  

## <a name="next-steps"></a>后续步骤

此过程仅粗略介绍使用历史调试可以完成的事项。

- 若要查看在调试时的快照，请参阅[检查上一应用程序状态使用 IntelliTrace](../debugger/view-historical-application-state.md)。
- 要了解有关不同设置和导航线中不同按钮的效果的详细信息，请参阅 [IntelliTrace 功能](../debugger/intellitrace-features.md)。