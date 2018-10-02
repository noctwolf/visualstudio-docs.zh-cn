---
title: CA1058： 类型不应扩展某些基类型 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d4eb5b13813ca8bf06a64c638f399186a88a17c4
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587518"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058：类型不应扩展某些基类型
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA1058： 类型不应扩展某些基类型](https://docs.microsoft.com/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)。

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 外部可见的类型扩展某些基类型。 目前，此规则将报告从以下类型派生的类型：

-   <xref:System.ApplicationException?displayProperty=fullName>

-   <xref:System.Xml.XmlDocument?displayProperty=fullName>

-   <xref:System.Collections.CollectionBase?displayProperty=fullName>

-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>

-   <xref:System.Collections.Queue?displayProperty=fullName>

-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

-   <xref:System.Collections.SortedList?displayProperty=fullName>

-   <xref:System.Collections.Stack?displayProperty=fullName>

## <a name="rule-description"></a>规则说明
 有关[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]版本 1 中，会建议派生新异常从<xref:System.ApplicationException>。 已更改的建议和新的异常应派生自<xref:System.Exception?displayProperty=fullName>或在其子类之一<xref:System>命名空间。

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



