---
title: CA1058:类型不应扩展某些基类型
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4157316756e4b180f6fb49082bf60927ddb43707
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714794"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058:类型不应扩展某些基类型

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因

一种类型扩展了以下基本类型之一：

- <xref:System.ApplicationException?displayProperty=fullName>
- <xref:System.Xml.XmlDocument?displayProperty=fullName>
- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.DictionaryBase?displayProperty=fullName>
- <xref:System.Collections.Queue?displayProperty=fullName>
- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>
- <xref:System.Collections.SortedList?displayProperty=fullName>
- <xref:System.Collections.Stack?displayProperty=fullName>

默认情况下，此规则只看起来在外部可见的类型，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

异常应派生自<xref:System.Exception?displayProperty=fullName>或在其子类之一<xref:System>命名空间。

不创建一个子类<xref:System.Xml.XmlDocument>如果你想要创建的基础对象模型或数据源的 XML 视图。

### <a name="non-generic-collections"></a>非泛型集合

使用和/或扩展尽可能的泛型集合。 除非以前交付之后不会扩展在代码中，非泛型集合。

**不正确的用法的示例**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

**正确用法的示例**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复与此规则的冲突，派生从不同的基类型或泛型集合类型。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止有关显示此规则冲突的警告<xref:System.ApplicationException>。 则可以安全地禁止有关显示此规则冲突的警告<xref:System.Xml.XmlDocument>。 安全地禁止显示非泛型集合有关的警告，如果代码以前发布它。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```ini
dotnet_code_quality.ca1058.api_surface = private, internal
```

此类别 （设计） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。