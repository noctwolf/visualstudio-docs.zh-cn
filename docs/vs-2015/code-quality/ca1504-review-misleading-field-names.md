---
title: CA1504： 检查令人误解的字段名 |Microsoft Docs
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
- ReviewMisleadingFieldNames
- CA1504
helpviewer_keywords:
- CA1504
- ReviewMisleadingFieldNames
ms.assetid: 94136ff1-4aaf-4dc2-9170-48c171ab7499
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c927457e2e16f19c221204ba445dad6c127da850
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49878383"
---
# <a name="ca1504-review-misleading-field-names"></a>CA1504：检查令人误解的字段名
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ReviewMisleadingFieldNames|
|CheckId|CA1504|
|类别|Microsoft.Maintainability|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 实例字段的名称以"s_"或名称的开头`static`(`Shared`中[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) 以"m_"开头的字段。

## <a name="rule-description"></a>规则说明
 以"s_"开头的字段名称与相关联的静态数据由多个用户。 同样，以"m_"开头的字段名称相关联的实例 （成员） 数据。 对于更轻松地维护代码，名称应遵循通常使用的约定。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，请使用相应的前缀重命名字段。 另外，还可以使该字段通过添加或删除与当前后缀相符`static`修饰符。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。



