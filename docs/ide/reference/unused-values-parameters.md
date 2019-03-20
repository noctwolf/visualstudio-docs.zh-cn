---
title: 未使用的值和参数
ms.date: 02/15/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: afcf85fff188853890b86cf7deb13b2457f5e0b8
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58157693"
---
# <a name="unused-expression-values-and-parameters"></a>未使用的表达式值和参数

此重构适用于：

- C#
- Visual Basic

**功能：** 渐隐未使用的参数并为未使用的表达式值生成警告。

**使用时机：** 有未使用的参数或表达式值。

操作原因：有时很难判断是否不再使用某个值或参数。 通过渐隐这些值或发出警告，可以直观地了解可以删除的代码。

## <a name="unused-expression-values-and-parameters-diagnostic"></a>未使用的表达式值和参数诊断

1. 有任何未使用的表达式值或参数。
2. 未使用的参数显示渐隐。未使用的表达式值会收到一条警告。

  ![未使用的参数](media/unused-parameter.png)
  ![未使用的值](media/unused-value.png)

## <a name="see-also"></a>请参阅

- [重构](../refactoring-in-visual-studio.md)
- [针对 .NET 开发人员的提示](../../ide/visual-studio-2017-for-dotnet-developers.md)
