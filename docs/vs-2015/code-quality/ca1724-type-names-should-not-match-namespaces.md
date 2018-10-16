---
title: CA1724： 类型名不应与命名空间 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 64999653e326cc99ca9b1880966406dde41ce52e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49246750"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724：类型名不应与命名空间冲突
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因
 类型名称匹配[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]不区分大小写的比较中的命名空间名称。

## <a name="rule-description"></a>规则说明
 类型名称不应该与 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 类库中定义的命名空间的名称匹配。 与该规则冲突将使库的可用性下降。

## <a name="how-to-fix-violations"></a>如何解决冲突
 选择的名称不匹配的类型名称[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]类库命名空间。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 对于新开发，没有已知情况下，必须在此禁止显示此规则的警告。 禁止显示警告之前，请仔细考虑如何库用户可能会被搞糊涂了匹配的名称。 发布库，您可能需要禁止显示此规则的警告。



