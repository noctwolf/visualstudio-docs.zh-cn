---
title: CA1814:与多维数组相比，首选使用交错数组
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
helpviewer_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
ms.assetid: b1ccf563-2ec8-42e5-b89c-731a9de1ea1d
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 281f29c82eed9133f1ee89ee7ac369bafdf6603a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53860788"
---
# <a name="ca1814-prefer-jagged-arrays-over-multidimensional"></a>CA1814:与多维数组相比，首选使用交错数组

|||
|-|-|
|TypeName|PreferJaggedArraysOverMultidimensional|
|CheckId|CA1814|
|类别|Microsoft.Performance|
|是否重大更改|重大|

## <a name="cause"></a>原因
 成员被声明为多维数组。

## <a name="rule-description"></a>规则说明
 交错数组是元素为数组的数组。 构成元素的数组可以是不同的大小，以减少某些数据集的浪费空间。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请更改到交错数组多维数组。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 禁止显示此规则的警告，如果多维数组不会浪费空间。

## <a name="example"></a>示例
 下面的示例演示了交错和多维数组的声明。

 [!code-vb[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/VisualBasic/ca1814-prefer-jagged-arrays-over-multidimensional_1.vb)]
 [!code-csharp[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/CSharp/ca1814-prefer-jagged-arrays-over-multidimensional_1.cs)]