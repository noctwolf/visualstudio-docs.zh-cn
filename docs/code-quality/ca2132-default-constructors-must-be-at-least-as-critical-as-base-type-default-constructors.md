---
title: CA2132：默认构造函数必须至少与基类型默认构造函数具有同样的关键性
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2132
ms.assetid: e758afa1-8bde-442a-8a0a-bd1ea7b0ce4d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c9ec028dd4e094612736bcd1970be0b59e8a263e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors"></a>CA2132：默认构造函数必须至少与基类型默认构造函数具有同样的关键性
|||
|-|-|
|TypeName|DefaultConstructorsMustHaveConsistentTransparency|
|CheckId|CA2132|
|类别|Microsoft.Security|
|是否重大更改|重大|

> [!NOTE]
>  此警告仅应用于运行 CoreCLR （特定于 Silverlight 的 Web 应用程序的 clr 的版本） 的代码。

## <a name="cause"></a>原因
 派生类的默认构造函数的透明特性不是基类的同样关键时的透明度。

## <a name="rule-description"></a>规则说明
 类型和成员具有<xref:System.Security.SecurityCriticalAttribute>无法供 Silverlight 应用程序代码。 安全关键类型和成员只能供 .NET Framework for Silverlight 类库中的受信任代码使用。 因为派生类中的某个公共或受保护构造必须有与其基类相同或更大的透明度，所以不能从标记为 SecurityCritical 的类派生应用程序中的类。

 对于 CoreCLR 平台代码，如果基类型具有一个公共或受保护的非透明默认构造函数然后派生的类型必须遵循的默认构造函数继承规则。 派生的类型还必须具有默认构造函数，并且该构造函数必须至少为基类型的关键的默认构造函数。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决冲突，删除类型或不是从安全非透明类型。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不要禁止显示此规则的警告。 违反此规则由应用程序代码将导致拒绝从中加载该类型与 CoreCLR <xref:System.TypeLoadException>。

### <a name="code"></a>代码
 [!code-csharp[FxCop.Security.CA2132.DefaultConstructorsMustHaveConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors_1.cs)]

### <a name="comments"></a>注释