---
title: CA1900:值类型字段应为可移植字段
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1900
- ValueTypeFieldsShouldBePortable
helpviewer_keywords:
- ValueTypeFieldsShouldBePortable
- CA1900
ms.assetid: 1787d371-389f-4d39-b305-12b53bc0dfb9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e823a58d7a2be45c43305320bd32175de7a3fad6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545389"
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900:值类型字段应为可移植字段

|||
|-|-|
|TypeName|ValueTypeFieldsShouldBePortable|
|CheckId|CA1900|
|类别|Microsoft.Portability|
|是否重大更改|是-如果该字段可以程序集外可见。<br /><br /> 无间断-如果该字段不是程序集外部可见。|

## <a name="cause"></a>原因
 此规则检查： 当用显式布局声明的结构封送到 64 位操作系统上的非托管代码时，将正确对齐。 IA-64 不允许访问未对齐的内存和进程将崩溃，如果不解决此冲突。

## <a name="rule-description"></a>规则说明
 具有包含 64 位操作系统上未对齐的字段会导致发生崩溃的显式布局的结构。

## <a name="how-to-fix-violations"></a>如何解决冲突
 小于 8 个字节的所有字段都必须是其大小的倍数的偏移量和 8 个字节的字段或详细信息都必须是 8 的倍数的偏移量。 另一种解决方案是使用`LayoutKind.Sequential`而不是`LayoutKind.Explicit`，如果合理。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 仅当其出现在错误中，应禁止显示此警告。