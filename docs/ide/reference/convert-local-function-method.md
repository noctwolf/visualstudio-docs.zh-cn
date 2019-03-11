---
title: 将本地函数转换为方法
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 55c82aa896de5c3f3bf18468a1da98253a3def74
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57324672"
---
# <a name="convert-local-function-to-method"></a>将本地函数转换为方法

此重构适用于：

- C#
- Visual Basic

**功能：** 将本地函数转换为方法

**使用时机：** 你希望将一个本地函数在当前本地上下文之外定义。

操作原因：你可能需要将本地函数转换为方法，以便可以在本地上下文之外调用它。 本地函数变得太长时，可能需要将其转换为方法。 在单独的方法中定义它，使代码更容易读取。

## <a name="convert-local-function-to-method-refactoring"></a>将本地函数转换为方法重构

1. 请将光标置于本地函数。

    ![将本地函数转换为方法](media/convert-local-function-to-method.png)

2. 按“Ctrl”+**。** 触发“快速操作和重构”菜单。

    ![将本地函数转换为方法 codefix](media/convert-local-function-to-method-codefix.png)

2. 按 Enter 接受重构。

    ![将本地函数转换为方法结果](media/convert-local-function-to-method-result.png)

## <a name="see-also"></a>请参阅

- [重构](../refactoring-in-visual-studio.md)
- [针对 .NET 开发人员的提示](../../ide/visual-studio-2017-for-dotnet-developers.md)
