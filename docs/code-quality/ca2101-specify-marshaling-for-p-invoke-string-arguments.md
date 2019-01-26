---
title: CA2101:指定对 P-Invoke 字符串自变量进行封送处理
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- SpecifyMarshalingForPInvokeStringArguments
- CA2101
helpviewer_keywords:
- CA2101
- SpecifyMarshalingForPInvokeStringArguments
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 52f7e6e0a09bf4b6b11d5cbdab3ab86cfa79724c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971515"
---
# <a name="ca2101-specify-marshaling-for-pinvoke-string-arguments"></a>CA2101:指定对 P/Invoke 字符串自变量进行封送处理

|||
|-|-|
|TypeName|SpecifyMarshalingForPInvokeStringArguments|
|CheckId|CA2101|
|类别|Microsoft.Globalization|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 平台调用成员允许部分受信任调用方具有一个字符串参数，并且不显式封送字符串。

## <a name="rule-description"></a>规则说明
 当你从 Unicode 转换为 ANSI 时，就可以不是所有 Unicode 字符，可以都表示特定的 ANSI 代码页。 *最佳匹配映射*尝试解决此问题，只需替换不能表示的字符的字符。 此功能的使用可能导致潜在的安全漏洞，因为您无法控制选择的字符。 例如，恶意代码会有意创建一个包含在特定代码页中，找不到该文件系统的特殊字符会转换为的字符的 Unicode 字符串 '..' 或 /。 另请注意的特殊字符的安全检查经常发生之前将字符串转换为 ANSI。

 对于非托管的转换，mb 的磁盘到 WChar 默认值为最佳的映射。 除非显式禁用最佳的映射，你的代码可能包含可利用的安全漏洞，由于此问题。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，显式封送字符串数据类型。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示一个方法，违反了此规则，并展示了如何解决冲突。

 [!code-csharp[FxCop.Security.PinvokeAnsiUnicode#1](../code-quality/codesnippet/CSharp/ca2101-specify-marshaling-for-p-invoke-string-arguments_1.cs)]