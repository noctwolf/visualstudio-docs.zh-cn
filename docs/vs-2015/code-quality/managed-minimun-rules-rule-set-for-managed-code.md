---
title: 托管最少量规则规则设置对于托管代码 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f67b9e28069a1717ad500b7e8895a363db715fda
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49251053"
---
# <a name="managed-minimun-rules-rule-set-for-managed-code"></a>托管代码的“托管最少量规则”规则集
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

托管最少量规则专注于在代码中，包括潜在安全漏洞、 应用程序崩溃和其他重要的逻辑和设计错误的最关键问题。 您应包含任何自定义规则集中设置为你的项目创建此规则。  
  
|规则|描述|  
|----------|-----------------|  
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|具有可释放字段的类型应该是可释放的|  
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|移除空终结器|  
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|应释放可释放的字段|  
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|重写 ValueType.Equals 时应重载相等运算符|



