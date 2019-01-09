---
title: “将类型移到匹配的文件”重构
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 793ae8f86bf4c4641a3170cde011a3912d0d38ef
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53870542"
---
# <a name="move-a-type-to-a-matching-file-refactoring"></a>“将类型移到匹配的文件”重构

此重构适用于：

- C#

- Visual Basic

**功能：** 移动选定的类型到具有相同名称的单独文件。

**使用时机：** 在想要分开的相同文件中有多个类、结构和接口等时。

操作原因：将多个类型置于相同的文件会使查找这些类型变得困难。 通过将类型移动到具有相同名称的文件，代码变得更具可读性且更易于导航。

## <a name="how-to"></a>操作说明

1. 将光标置于定义类型的类型名称中。 例如:

   ```csharp
   class Person
   ```

   ```vb
   Class Person
   ```

2. 接下来，执行以下操作之一：

   - 按“Ctrl”+**。**
   - 右键单击类型名称，并选择“快速操作和重构”

1. 选择菜单中的“将类型移到 TypeName.cs”，其中“TypeName”是选定类型的名称。

   此时，类型会移到项目中与它同名的文件中。

   - C#：

      ![内联结果 - C#](media/movetype-result-cs.png)

   - Visual Basic：

      ![内联结果 - Visual Basic](media/movetype-result-vb.png)

## <a name="see-also"></a>请参阅

- [重构](../refactoring-in-visual-studio.md)
