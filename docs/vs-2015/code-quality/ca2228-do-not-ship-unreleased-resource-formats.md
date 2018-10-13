---
title: CA2228： 不要发行未发布的资源格式 |Microsoft Docs
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
ms.openlocfilehash: 80f7b154aa89cf57d8a0e1e9de04a741a1f7413d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49230870"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228：不要发行未发布的资源格式
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
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



