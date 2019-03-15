---
title: CA1716:标识符不应与关键字冲突
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 279bcf3aecc2a637a7a36c2041ed63a72017a800
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57867727"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716:标识符不应与关键字冲突

|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因

命名空间、 类型、 名称或虚拟或接口成员匹配编程语言中的保留的关键字。

默认情况下，此规则仅查看外部可见的命名空间、 类型和成员，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

命名空间、 类型、 标识符和虚拟和接口成员不应与面向公共语言运行时的语言所定义的关键字。 根据使用的语言和关键字，编译器错误和二义性可以使库难以使用。

此规则检查针对以下语言中的关键字：

- Visual Basic
- C#
- C++/CLI

对于 Visual Basic 关键字，使用不区分大小写的比较，对于其他语言使用区分大小写的比较。

## <a name="how-to-fix-violations"></a>如何解决冲突

关键字的列表中选择不会出现的名称。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

如果您相信标识符不会混淆的 API，用户和库是在.NET 中的所有可用语言中可用，则可以禁止显示此规则的警告。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```
dotnet_code_quality.ca1716.api_surface = private, internal
```

此类别 （命名） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。