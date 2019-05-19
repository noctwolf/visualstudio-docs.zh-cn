---
title: CA1725:参数名应与基方法中的声明保持一致
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bbe62c830b7cd3454adbde8b1d3081af11ef1a6b
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841654"
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725:参数名应与基方法中的声明保持一致

|||
|-|-|
|TypeName|ParameterNamesShouldMatchBaseDeclaration|
|CheckId|CA1725|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因

方法重写中的参数名称不匹配基方法声明中参数的名称或该方法的接口声明中参数的名称。

默认情况下，此规则仅查看外部可见方法，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

以一致的方式命名重写层次结构中的参数可以提高方法重写的可用性。 如果派生方法中的参数名与基声明中的名称不同，可能会导致无法区分出该方法是基方法的重写还是该方法的新重载。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请重命名参数以匹配基声明。 解决方法是一项重大更改对 COM 可见方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不要禁止显示除以前发布的库中的 COM 可见方法的此规则的警告。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```ini
dotnet_code_quality.ca1725.api_surface = private, internal
```

此类别 （命名） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。