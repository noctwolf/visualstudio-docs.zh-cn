---
title: CA1724：类型名不应与命名空间冲突
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1f9e13f8e02712ba4d0a0a492a9a6588f7a8a5e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724：类型名不应与命名空间冲突
|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因
 类型名与匹配[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]不区分大小写的比较中的命名空间名称。

## <a name="rule-description"></a>规则说明
 类型名称不应该与 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 类库中定义的命名空间的名称匹配。 与该规则冲突将使库的可用性下降。

## <a name="how-to-fix-violations"></a>如何解决冲突
 选择的名称不匹配的类型名称[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]类库命名空间。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 对于新开发，没有已知会出现情况，必须在此禁止显示此规则的警告。 禁止显示警告之前，请仔细考虑如何你的库的用户也可能因匹配名称产生混淆。 发布库，你可能需要禁止显示此规则的警告。