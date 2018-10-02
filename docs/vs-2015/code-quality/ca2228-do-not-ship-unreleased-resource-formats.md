---
title: CA2228： 不要发行未发布的资源格式 |Microsoft Docs
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
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 84dc7c20f4109f7d66ed83b22fcec36dacc5eb3f
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587657"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228：不要发行未发布的资源格式
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA2228： 不要发行未发布的资源格式](https://docs.microsoft.com/visualstudio/code-quality/ca2228-do-not-ship-unreleased-resource-formats)。

|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 资源文件采用的版本生成[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]，当前不支持。

## <a name="rule-description"></a>规则说明
 通过使用的预发布版本生成的资源文件[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]可能无法用于受支持的.NET Framework 版本。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，生成使用受支持的版本资源[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]k。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。



