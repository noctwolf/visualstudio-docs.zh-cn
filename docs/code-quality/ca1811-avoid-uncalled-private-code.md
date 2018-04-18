---
title: CA1811： 避免使用未调用的私有代码 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- AvoidUncalledPrivateCode
- CA1811
helpviewer_keywords:
- CA1811
- AvoidUncalledPrivateCode
ms.assetid: aadbba74-7821-475f-8980-34d17c0a0a8b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d9015fe8b7384046b621cd11600528cd76a97c1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca1811-avoid-uncalled-private-code"></a>CA1811：避免使用未调用的私有代码
|||  
|-|-|  
|TypeName|AvoidUncalledPrivateCode|  
|CheckId|CA1811|  
|类别|Microsoft.Performance|  
|是否重大更改|非重大|  
  
## <a name="cause"></a>原因  
 私有或内部 （程序集级别） 成员在程序集中没有调用方、 由公共语言运行时，不调用和不会被调用的委托。 此规则不检查下列成员：  
  
-   显式接口成员。  
  
-   静态构造函数。  
  
-   序列化构造函数。  
  
-   使用标记方法<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName>或<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>。  
  
-   重写的成员。  
  
## <a name="rule-description"></a>规则说明  
 此规则会报告误报入口点会发生，如果当前未标识由规则逻辑。 此外，编译器可能将不可调用的代码发出到程序集。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 若要修复与此规则的冲突，删除不可调用的代码，或添加调用它的代码。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 则可以安全地禁止显示此规则的警告。  
  
## <a name="related-rules"></a>相关的规则  
 [CA1812：避免未实例化的内部类](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1801：检查未使用的参数](../code-quality/ca1801-review-unused-parameters.md)  
  
 [CA1804：移除未使用的局部变量](../code-quality/ca1804-remove-unused-locals.md)