---
title: "在 Visual Studio 中删除无法访问的代码重构操作 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: kuhlenh
ms.author: kaseyu
manager: ghogen
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: 12b6910aad6399b72b3e4bc10e6b857cc98c09bb
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2018
---
# <a name="remove-unreachable-code-in-c"></a>删除无法访问的代码 (C#) #

功能：删除永远不执行的代码

时机：程序无法访问代码片段，使得该代码片段没有存在的必要性时。

原因：通过删除永远不会执行的多余代码来提高可读性和可维护性。

方法：

1. 将无法访问的代码淡化后，将光标置于其中的任意位置：

![淡化后的无法访问的代码](media/unreachablecode-faded-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“删除无法访问的代码”。
   * **鼠标**
     * 右键单击代码，选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“删除无法访问的代码”。

1. 对更改感到满意时，按 Enter 或单击菜单中的修复，即可提交所做的更改。

示例:

```csharp
// Before
private void Method()
{
    throw new Exception(nameof(Method));
    Console.WriteLine($"Exception for method {nameof(Method)}");
}

// Remove unreachable code

// After
private void Method()
{
    throw new Exception(nameof(Method));
}
```

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)  
[预览更改](../../ide/preview-changes.md)