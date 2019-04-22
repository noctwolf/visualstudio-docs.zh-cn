---
title: 将 foreach 循环转换为 LINQ
ms.date: 02/20/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 18c5b01aed925bf458e1c8779a2f41ea1a2d98a4
ms.sourcegitcommit: 7eb85d296146186e7a39a17f628866817858ffb0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2019
ms.locfileid: "59504063"
---
# <a name="convert-foreach-loop-to-linq"></a>将 foreach 循环转换为 LINQ

此重构适用于：

- C#

**功能：** 可以使用 IEnumerables 轻松地将 foreach 循环转换为 LINQ 查询或 LINQ 调用窗体（也称为 LINQ 方法）。

**使用时机：** foreach 循环中使用更倾向于作为 LINQ 查询读取的 IEnumerable 时。

操作原因：有时用户可能更倾向于使用 LINQ 语法而不是 foreach 循环。 [LINQ](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq) 使查询成为 C# 中的一流语言构造。 LINQ 可以减少文件中的代码量，使其更易于读取，并允许不同的数据源具有类似的查询表达式模式。

> [!NOTE]
> LINQ 语法的性能通常不如 foreach 循环。 在使用 LINQ 提高代码的可读性时，最好了解可能导致的任何性能折中。

## <a name="convert-foreach-loop-to-linq-refactoring"></a>将 foreach 循环转换为 LINQ 重构

1. 请将光标置于 `foreach` 关键字。

    ![使用 IEnumerable 的 Foreach](media/convert-foreach-to-LINQ.png)

2. 按“Ctrl”+**。** 触发“快速操作和重构”菜单。

   ![转换为 LINQ 菜单](media/convert-foreach-to-LINQ-codefix.png)

3. 选择“转换为 LINQ”或“转换为 Linq (调用窗体)”

   ![LINQ 查询结果](media/convert-foreach-to-LINQ-result.png)
   
   ![LINQ 调用窗体结果](media/convert-foreach-to-LINQ-callform-result.png)
   
### <a name="sample-code"></a>代码示例

```csharp
using System.Collections.Generic;

public class Class1
{
    public void MyMethod()
    {
        var greetings = new List<string>()
            { "hi", "yo", "hello", "howdy" };

        IEnumerable<string> enumerable()
        {
            foreach (var greet in greetings)
            {
                if (greet.Length < 3)
                {
                    yield return greet;
                }
            }

            yield break;
        }
    }
}
```

## <a name="see-also"></a>请参阅

- [重构](../refactoring-in-visual-studio.md)
- [预览更改](../../ide/preview-changes.md)
- [针对 .NET 开发人员的提示](../../ide/visual-studio-2017-for-dotnet-developers.md)
