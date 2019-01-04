---
title: CA2124:在外部 try 块中包装易受攻击的 finally 子句
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a15c5019dd5f3084ff250015e8a9725f4dbf971
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53829285"
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124:在外部 try 块中包装易受攻击的 finally 子句

|||
|-|-|
|TypeName|WrapVulnerableFinallyClausesInOuterTry|
|CheckId|CA2124|
|类别|Microsoft.Security|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 在版本 1.0 和 1.1 版.NET Framework 中，包含公共或受保护方法`try` / `catch` / `finally`块。 `finally`块似乎要重置安全状态，并且不括在`finally`块。

## <a name="rule-description"></a>规则说明
 此规则查找`try` / `finally`面向版本 1.0 和 1.1 版可能受到恶意的异常筛选器的调用堆栈中存在的.NET framework 的代码中的块。 如果模拟等敏感操作发生在 try 块中，且会引发异常，该筛选器可以执行之前`finally`块。 对于模拟的示例中，这意味着该筛选器将执行作为被模拟用户。 筛选器是目前仅在 Visual Basic 中实施。

> [!NOTE]
> 在版本 2.0 及更高版本的.NET Framework 中，运行时自动保护`try` / `catch` /  `finally`重置该方法内直接发生的情况下阻止从恶意的异常筛选器，包含异常块。

## <a name="how-to-fix-violations"></a>如何解决冲突
 放置未包装`try` / `finally`在外部 try 块中。 请参阅后面的第二个示例。 这会强制`finally`之前筛选器代码执行。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="pseudo-code-example"></a>伪代码示例

### <a name="description"></a>描述

下面伪代码说明此规则检测到的模式。

```csharp
try {
   // Do some work.
   Impersonator imp = new Impersonator("John Doe");
   imp.AddToCreditCardBalance(100);
}
finally {
   // Reset security state.
   imp.Revert();
}
```

下面的伪代码演示的模式可用于保护你的代码和满足此规则。

```csharp
try {
     try {
        // Do some work.
     }
     finally {
        // Reset security state.
     }
}
catch()
{
    throw;
}
```