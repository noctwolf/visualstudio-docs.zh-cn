---
title: CA1726：使用首选词条
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UsePreferredTerms
- CA1726
helpviewer_keywords:
- UsePreferredTerms
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c81bd543a6695adcea37db5ab8570ff7749c0160
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551449"
---
# <a name="ca1726-use-preferred-terms"></a>CA1726：使用首选词条

|||
|-|-|
|TypeName|UsePreferredTerms|
|CheckId|CA1726|
|类别|Microsoft.Naming|
|是否重大更改|-对程序集引发时中断<br /><br /> 无间断-时在类型参数时触发|

## <a name="cause"></a>原因

在外部可见的标识符的名称中，包括一个存在首选备用词条的词条。 或者，名称包括术语标志或标志。

## <a name="rule-description"></a>规则说明

此规则将分析为标记的标识符。 每个单个标记和每个连续的双标记组合到规则和任何自定义词典的已弃用部分生成的条款进行比较。 下表显示了内置规则以及其首选备用词条的条款。

|过时的术语|首选的术语|
|-------------------|--------------------|
|`Arent`|`AreNot`|
|`Cancelled`|`Canceled`|
|`Cant`|`Cannot`|
|`ComPlus`|`EnterpriseServices`|
|`Couldnt`|`CouldNot`|
|`Didnt`|`DidNot`|
|`Doesnt`|`DoesNot`|
|`Dont`|`DoNot`|
|`Flag` 或 `Flags`|没有任何替换词。 请勿使用。|
|`Hadnt`|`HadNot`|
|`Hasnt`|`HasNot`|
|`Havent`|`HaveNot`|
|`Indices`|`Indexes`|
|`Isnt`|`IsNot`|
|`LogIn`|`LogOn`|
|`LogOut`|`LogOff`|
|`Shouldnt`|`ShouldNot`|
|`SignOn`|`SignIn`|
|`SignOff`|`SignOut`|
|`Wasnt`|`WasNot`|
|`Werent`|`WereNot`|
|`Wont`|`WillNot`|
|`Wouldnt`|`WouldNot`|
|`Writeable`|`Writable`|

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请替换首选备用词条中的术语。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 仅当标识符的名称是有意而为且明确地与原始字词而不是首选术语相关，禁止显示此规则的警告。

## <a name="related-rules"></a>相关的规则
 [命名警告](../code-quality/naming-warnings.md)