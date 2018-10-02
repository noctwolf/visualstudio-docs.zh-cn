---
title: 调试 LINQ |Microsoft Docs
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
helpviewer_keywords:
- debugging, LINQ
- LINQ, viewing results in debugger
- LINQ, debugging
- LINQ, stepping
- LINQ, edit and continue
ms.assetid: dbae26cb-ac5f-4312-b474-b9f29714f4c6
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29e5a598c1c9d0d605267ed0894715eb18589136
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477195"
---
# <a name="debugging-linq"></a>调试 LINQ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[调试 LINQ](https://docs.microsoft.com/visualstudio/debugger/debugging-linq)。  
  
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 支持对语言集成查询 (LINQ) 代码进行调试，但是有一些限制。 大多数调试功能都使用 LINQ 语句，其中包括单步执行、设置断点以及在调试器窗口中查看结果。 本主题介绍 LINQ 调试的主要限制。  
  
##  <a name="BKMK_ViewingLINQResults"></a> 查看 LINQ 结果  
 使用数据提示功能、“监视”窗口和“快速监视”对话框，可以查看 LINQ 语句的结果。 在使用源窗口时，可以将指针停放在源窗口中的某个查询上，这样会出现“数据提示”。 可以将一个 LINQ 变量复制并粘贴到“监视”窗口或“快速监视”对话框中。  
  
 在 LINQ 中，查询不会在创建或声明时进行计算，而只在使用时才进行计算。 因此，查询经过计算后才具有值。 有关查询创建和计算的完整说明，请参阅[LINQ 查询 (C#) 简介](http://msdn.microsoft.com/library/37895c02-268c-41d5-be39-f7d936fa88a8)或[编写你的第一个 LINQ 查询](http://msdn.microsoft.com/library/4affb732-3e9b-4479-aa31-1f9bd8183cbe)。  
  
 若要显示某个查询的结果，调试器必须计算该查询。 在调试器中查看 LINQ 查询结果时，这种隐式计算具有的某些影响，应当加以考虑：  
  
-   查询的每次计算都需要时间。 展开结果节点需要时间。 对于某些查询，反复计算可能导致性能显著下降。  
  
-   计算查询可能产生副作用，这些副作用表现为对数据的值或程序状态的更改。 不是所有查询都具有副作用。 若要确定查询是否可以安全计算而不具有副作用，必须理解实现查询的代码。  
  
##  <a name="BKMK_SteppingAndLinq"></a> 单步执行和 LINQ  
 调试 LINQ 代码时，单步执行具有一些你应知道的行为差异。  
  
### <a name="linq-to-sql"></a>LINQ to SQL  
 在 LINQ to SQL 查询中，谓词代码不受调试器控制。 因此，无法进入并单步执行谓词代码。 任何编译为表达式树的查询都会产生不受调试器控制的代码。  
  
### <a name="stepping-in-visual-basic"></a>Visual Basic 中的单步执行  
 在单步执行 Visual Basic 程序且调试器遇到查询声明时，调试器不会进入并单步执行该声明，而是将整个声明作为单个语句突出显示。 发生此行为的原因是查询直到调用时才进行计算。 有关详细信息，请参阅[在 Visual Basic 中的 LINQ 简介](http://msdn.microsoft.com/library/3047d86e-0d49-40e2-928b-dc02e46c7984)。  
  
 如果单步执行下面的代码示例，则调试器会将查询声明或查询创建作为单个语句突出显示。  
  
```  
Function MyFunction(ByVal x As Char)  
    Return True  
End Function  
  
Sub Main()  
    'Query creation  
    Dim x = From it In "faoaoeua" _  
            Where MyFunction(it) _  
            Select New With {.a = it}  
  
    ' Query execution  
    For Each cur In x  
        Console.WriteLine(cur.ToString())  
    Next  
End Sub  
```  
  
 当你再次单步执行时，调试器会突出显示 `For Each cur In x`。 在下一步中，调试器会进入并单步执行函数 `MyFunction`。 在单步执行 `MyFunction` 后，调试器跳回到 `Console.WriteLine(cur.ToSting())`。 调试器在任何时候都不会单步执行查询声明中的谓词代码，尽管调试器的确会计算该代码。  
  
### <a name="replacing-a-predicate-with-a-function-to-enable-stepping-visual-basic"></a>用函数替换谓词以启用单步执行 (Visual Basic)  
 如果必须单步执行谓词代码以便达到调试目的，则可以将谓词替换为对包含原始谓词代码的函数的调用。 例如，假定你具有下面的代码：  
  
```  
Dim items() as integer ={1, 2, 3, 4, 5, 6, 7, 8, 9, 10}  
  
' Get the even numbers  
Dim query = From nextInt in items Where nextInt Mod 2 = 0 Select nextInt  
  
For each item in query  
      Console.WriteLine(item)  
Next  
```  
  
 可以将谓词代码移动至一个新函数，该函数称为 `IsEven`：  
  
```  
Dim items () as integer ={1, 2, 3, 4, 5, 6, 7, 8, 9, 10}  
  
' Get the even numbers  
Dim query = From nextInt in items Where IsEven(nextInt) Select nextInt  
  
For each item in query  
      Console.WriteLine(item)  
Next  
...   
Function IsEven(item As =Integer) as Boolean  
      Return item Mod 2 = 0  
End Function  
```  
  
 修改后的查询在每次遍历 `IsEven` 时都会调用函数 `items`。 你可以使用调试器窗口来查看每个“item”是否满足指定条件，并且可以单步执行 `IsEven` 中的代码。 此示例中的谓词相当简单。 但是，如果必须调试一个更复杂的谓词，这种技术也会十分有用。  
  
##  <a name="BKMK_EditandContinueNotSupportedforLINQ"></a> 编辑并继续 LINQ 不支持  
 “编辑并继续”不支持对 LINQ 查询的更改。 如果在调试会话过程中添加、移除或更改 LINQ 语句，则会出现一个对话框，告知你“编辑并继续”不支持该更改。 此时，可以撤消更改，或停止调试会话并对编辑的代码重新启动新会话。  
  
 此外，“编辑并继续”不支持更改 LINQ 语句中使用的变量的类型或值。 同样，可以撤消更改，或停止并重新启动调试会话。  
  
 在 C# 中，不能对包含 LINQ 查询的方法中的任何代码使用“编辑并继续”。  
  
 在 Visual Basic 中，可以对非 LINQ 代码使用“编辑并继续”，即使是在包含 LINQ 查询的方法中，也是如此。 在 LINQ 语句前，可以添加或移除代码，即使这些更改会影响 LINQ 查询的行号，也是如此。 非 LINQ 代码的 Visual Basic 调试体验与引入 LINQ 前是一样的。 但是，除非要停止调试以应用更改，否则不能更改、添加或移除 LINQ 查询。  
  
## <a name="see-also"></a>请参阅  
 [SQL 调试](http://msdn.microsoft.com/en-us/f27c17e6-1d90-49f2-9fc0-d02e6a27f109)   
 [Side Effects and Expressions](http://msdn.microsoft.com/library/e1f8a6ea-9e19-481d-b6bd-df120ad3bf4e)   
 [管理调试器的异常](../debugger/managing-exceptions-with-the-debugger.md)   
 [LINQ 查询简介 (C#)](http://msdn.microsoft.com/library/37895c02-268c-41d5-be39-f7d936fa88a8)   
 [Visual Basic 中的 LINQ 简介](http://msdn.microsoft.com/library/3047d86e-0d49-40e2-928b-dc02e46c7984)



