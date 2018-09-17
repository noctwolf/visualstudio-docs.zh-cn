---
title: CA1050：在命名空间中声明类型
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5bff984d9ea11ba8fd7f2e42deb5898f04da7d44
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548474"
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050：在命名空间中声明类型

|||
|-|-|
|TypeName|DeclareTypesInNamespaces|
|CheckId|CA1050|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 命名的命名空间范围内定义了一个公共或受保护的类型。

## <a name="rule-description"></a>规则说明
 在命名空间，以防止名称冲突，并作为一种方法来组织对象层次结构中的相关的类型声明类型。 任何命名的命名空间之外的类型是不能在代码中引用全局命名空间中。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，将类型置于一个命名空间中。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 虽然永远不会需要禁止显示此规则的警告，是安全地执行此操作时将程序集将永远不与其他程序集一起使用。

## <a name="example"></a>示例
 下面的示例演示具有类型外部命名空间中，未正确声明一个库和具有相同名称的命名空间中声明的类型。

 [!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_1.cs)]
 [!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_1.vb)]

## <a name="example"></a>示例
 下面的应用程序使用以前已定义的库。 请注意，外部命名空间声明的类型时，将创建名称`Test`未由命名空间限定。 另请注意，若要访问`Test`中键入`Goodspace`，命名空间名称是必需的。

 [!code-csharp[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_2.cs)]
 [!code-vb[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_2.vb)]