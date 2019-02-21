---
title: 将匿名类型转换为类
ms.date: 02/13/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: e3613f365b2510111f6854087a597df387ab1a4c
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335758"
---
# <a name="convert-anonymous-type-to-class"></a>将匿名类型转换为类

此重构适用于：

- C#

**功能：** 将匿名类型转换为类。

**使用时机：** 有要继续在类中生成的匿名类型。

操作原因：如果仅在本地使用，则匿名类型很有用。 随着代码的增多，最好能够使用简单的方法将其提升到类中。

## <a name="how-to"></a>操作说明

1. 请将光标放置在匿名类型中。
2. 按“Ctrl”+**。** 触发“快速操作和重构”菜单。

   ![将匿名类型转换为类](media/convert-anon-to-class.png)

2. 按 Enter 接受重构。

   ![将匿名类型转换为接受的类](media/convert-anon-to-class-complete.png)

## <a name="see-also"></a>请参阅

- [重构](../refactoring-in-visual-studio.md)
