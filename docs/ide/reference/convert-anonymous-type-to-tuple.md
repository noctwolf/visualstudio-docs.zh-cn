---
title: 将匿名类型转换为元组
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: b7a53aa8f329c1cdedc0cedff7e56b3f6dfa2f2a
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335755"
---
# <a name="convert-anonymous-type-to-tuple"></a>将匿名类型转换为元组

此重构适用于：

- C#

**功能：** 将匿名类型转换为元组。

**使用时机：** 有符合元组资格的匿名类型。

操作原因：[元组](/dotnet/csharp/tuples)有助于保持语法轻量级。 此快速操作可以更容易地利用此 C# 功能。

## <a name="how-to"></a>操作说明

1. 请将光标放置在匿名类型中。
2. 按“Ctrl”+**。** 触发“快速操作和重构”菜单。

   ![将匿名类型转换为元组](media/convert-anon-to-tuple.png)

2. 按 Enter 接受重构。

   ![将匿名类型转换为元组](media/convert-anon-to-tuple-complete.png)

## <a name="see-also"></a>请参阅

- [重构](../refactoring-in-visual-studio.md)
