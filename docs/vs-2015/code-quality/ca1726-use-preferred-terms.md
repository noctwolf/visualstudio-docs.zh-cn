---
title: CA1726： 使用首选的词条 |Microsoft Docs
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
- UsePreferredTerms
- CA1726
helpviewer_keywords:
- UsePreferredTerms
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c17514d00be7b0a3303b1c5bf703702fe564e0d1
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49220514"
---
# <a name="ca1726-use-preferred-terms"></a>CA1726：使用首选词条
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 2017 的最新文档，请参阅[CA1726： 使用首选的词条](https://docs.microsoft.com/visualstudio/code-quality/ca1726-use-preferred-terms)docs.microsoft.com 上。  
  
|||  
|-|-|  
|TypeName|UsePreferredTerms|  
|CheckId|CA1726|  
|类别|Microsoft.Naming|  
|是否重大更改|-对程序集引发时中断<br /><br /> 无间断-时在类型参数时触发|  
  
## <a name="cause"></a>原因  
 在外部可见的标识符的名称中，包括一个存在首选备用词条的词条。 或者，名称中包含术语标志或标志。  
  
## <a name="rule-description"></a>规则说明  
 此规则将分析为标记的标识符。 每个单个标记和每个连续的双标记组合到规则和任何自定义词典的已弃用部分生成的条款进行比较。 下表显示了内置规则以及其首选备用词条的条款。  
  
|过时的术语|首选的术语|  
|-------------------|--------------------|  
|不是|后面|  
|已取消|Canceled|  
|无法|不能|  
|ComPlus|EnterpriseServices|  
|无法|不能|  
|Didnt|DidNot|  
|无法|开头|  
|不|不|  
|标志或标志|没有任何替换词。 请勿使用。|  
|尚未|HadNot|  
|尚未|HasNot|  
|尚未|HaveNot|  
|索引|索引|  
|不是|IsNot|  
|登录名|登录|  
|注销|注销|  
|Shouldnt|ShouldNot|  
|登录|登录|  
|签字认可|注销|  
|Wasnt|WasNot|  
|没有|未|  
|未|翻译已经不再|  
|Wouldnt|WouldNot|  
|可写|可写|  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 若要修复此规则的冲突，请替换首选备用词条中的术语。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 仅当标识符的名称是有意而为且明确地与原始字词而不是首选术语相关，禁止显示此规则的警告。  
  
## <a name="related-rules"></a>相关的规则  
 [命名警告](../code-quality/naming-warnings.md)

