---
title: CA1044： 属性不应是只写 |Microsoft Docs
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
- PropertiesShouldNotBeWriteOnly
- CA1044
helpviewer_keywords:
- CA1044
- PropertiesShouldNotBeWriteOnly
ms.assetid: 8386bf3a-b161-4841-bf8b-92591595aea9
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 732af1dcdeff669723f717dabe035a38640a8bf3
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47588527"
---
# <a name="ca1044-properties-should-not-be-write-only"></a>CA1044：属性不应是只写的
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA1044： 属性不应是只写](https://docs.microsoft.com/visualstudio/code-quality/ca1044-properties-should-not-be-write-only)。

|||
|-|-|
|TypeName|PropertiesShouldNotBeWriteOnly|
|CheckId|CA1044|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共或受保护属性具有 set 访问器，但不具有 get 访问器。

## <a name="rule-description"></a>规则说明
 获取提供给属性的读取访问权限的访问器和 set 访问器提供写访问权限。 虽然可以接受且经常需要使用只读属性，但设计准则禁止使用只写属性。 这是因为允许用户设置一个值，并阻止用户查看的值不提供任何安全性。 而且，如果没有读访问，将无法查看共享对象的状态，使其用处受到限制。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请添加到的属性 get 访问器。 或者，如果只写属性的行为有必要，请考虑将此属性转换为一种方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 强烈建议不禁止显示此规则的警告。

## <a name="example"></a>示例
 在以下示例中，`BadClassWithWriteOnlyProperty`是只写属性的类型。 `GoodClassWithReadWriteProperty` 包含更正后的代码。

 [!code-csharp[FxCop.Design.PropertiesNotWriteOnly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.PropertiesNotWriteOnly/cs/FxCop.Design.PropertiesNotWriteOnly.cs#1)]
 [!code-vb[FxCop.Design.PropertiesNotWriteOnly#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.PropertiesNotWriteOnly/vb/PropertiesNotWriteOnly.vb#1)]



