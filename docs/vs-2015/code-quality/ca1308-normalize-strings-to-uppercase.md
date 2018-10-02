---
title: CA1308： 将字符串规范化为大写 |Microsoft Docs
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
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8f5a40d412b8ea9616dd75d7e0424ba447b5a185
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47492625"
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308：将字符串规范化为大写
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA1308： 将字符串规范化为大写](https://docs.microsoft.com/visualstudio/code-quality/ca1308-normalize-strings-to-uppercase)。

|||
|-|-|
|TypeName|NormalizeStringsToUppercase|
|CheckId|CA1308|
|类别|Microsoft.Globalization|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 操作将规范化为小写的字符串。

## <a name="rule-description"></a>规则说明
 字符串应正常化为大写字母。 字符，当它们转换为小写，不能进行一次往返过程时一小组。 若要进行往返行程意味着若要将字符转换的区域设置到另一个区域设置的方式不同，表示的字符数据，再到准确地检索从已转换的字符的原始字符。

## <a name="how-to-fix-violations"></a>如何解决冲突
 更改操作将字符串转换为小写，以便将字符串转换为改为大写。 例如，将 `String.ToLower(CultureInfo.InvariantCulture)` 更改为 `String.ToUpper(CultureInfo.InvariantCulture)`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它是安全地禁止显示一条警告消息，当您不需要安全决策基于结果 （例如，当在 UI 中显示时）。

## <a name="see-also"></a>请参阅
 [全球化警告](../code-quality/globalization-warnings.md)



