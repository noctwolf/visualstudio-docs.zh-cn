---
title: CA2228：不要发行未发布的资源格式
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e2823933e4792dd6127ffbd4b1bfe5dfe1b71a0c
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547539"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228：不要发行未发布的资源格式
|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 资源文件采用的版本生成[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]，当前不支持。

## <a name="rule-description"></a>规则说明
 通过使用的预发布版本生成的资源文件[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]可能无法用于受支持的.NET Framework 版本。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，生成使用受支持的版本资源[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]k。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。