---
title: CA1713:事件不应具有 before 或 after 前缀
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- EventsShouldNotHaveBeforeOrAfterPrefix
- CA1713
helpviewer_keywords:
- CA1713
- EventsShouldNotHaveBeforeOrAfterPrefix
ms.assetid: 855772a4-aa9e-410b-88c1-c5fba1ca63da
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7c7955fe4570ec7bb8e7db56b715a28949a7142a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54939291"
---
# <a name="ca1713-events-should-not-have-before-or-after-prefix"></a>CA1713:事件不应具有 before 或 after 前缀

|||
|-|-|
|TypeName|EventsShouldNotHaveBeforeOrAfterPrefix|
|CheckId|CA1713|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因
 'Before' 或 'After' 的事件名称开头。

## <a name="rule-description"></a>规则说明
 事件名称应描述引发事件的操作。 若要命名按特定顺序引发的相关事件，请使用现在时或过去时指示一系列操作中的相对位置。 例如，当命名的一对事件引发时关闭资源时，您可以命名它关闭和已关闭，而不是应使用 BeforeClose 和 AfterClose。

 命名约定提供了通用的外观对于库面向公共语言运行时。 这会减少所需的新软件库，并会增加客户信心库由必须在托管代码中开发的专业知识的人学习曲线。

## <a name="how-to-fix-violations"></a>如何解决冲突
 从事件名称中删除前缀，并考虑将名称更改为使用现在时或过去时的谓词。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。