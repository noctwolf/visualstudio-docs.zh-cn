---
title: CA1307： 指定 StringComparison |Microsoft Docs
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
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2c96b8c895106337a8578b6662c0e61830b38f55
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587737"
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307：指定 StringComparison
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA1307： 指定 StringComparison](https://docs.microsoft.com/visualstudio/code-quality/ca1307-specify-stringcomparison)。

|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|类别|Microsoft.Globalization|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 字符串比较运算使用方法重载，不会设置<xref:System.StringComparison>参数。

## <a name="rule-description"></a>规则说明
 许多字符串运算，最重要<xref:System.String.Compare%2A>并<xref:System.String.Equals%2A>方法，提供一个重载接受<xref:System.StringComparison>枚举作为参数的值。

 每当重载存在接受<xref:System.StringComparison>参数，而不是不接受此参数的重载，则应使用。 通过显式设置此参数，你的代码通常是进行更清晰易懂、 更易于维护。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，请将字符串比较方法更改为接受的重载<xref:System.StringComparison>枚举用作参数。 例如： 更改`String.Compare(str1, str2)`到`String.Compare(str1, str2, StringComparison.Ordinal)`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告，当库或应用程序适用于有限的本地用户，并因此不会本地化。

## <a name="see-also"></a>请参阅
 [全球化警告](../code-quality/globalization-warnings.md) [CA1309： 使用序号 StringComparison](../code-quality/ca1309-use-ordinal-stringcomparison.md)



