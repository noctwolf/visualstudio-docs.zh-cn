---
title: CA1716： 标识符不应与关键字 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c695f66a096614621cee2f38aed3e8fd6d970bed
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716：标识符不应与关键字冲突
|||  
|-|-|  
|TypeName|IdentifiersShouldNotMatchKeywords|  
|CheckId|CA1716|  
|类别|Microsoft.Naming|  
|是否重大更改|重大|  
  
## <a name="cause"></a>原因  
 命名空间、 类型或虚拟或接口成员的名称与编程语言中的保留的关键字。  
  
## <a name="rule-description"></a>规则说明  
 命名空间、 类型，标识符和虚拟和接口成员不应与针对公共语言运行时的语言所定义的关键字。 根据使用的语言和关键字，编译器错误和多义性可以使库难以使用。  
  
 此规则检查针对以下语言中的关键字：  
  
-   Visual Basic  
  
-   C#  
  
-   C++/CLI  
  
 有关使用不区分大小写的比较[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]关键字和区分大小写比较用于其他语言。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 在关键字的列表中选择不会出现的名称。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 如果您确信的是，该标识符不混淆的 API，用户和库可用于所有可用语言中，你可以禁止显示此规则的警告[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]。