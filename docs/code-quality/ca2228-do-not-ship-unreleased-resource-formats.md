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
ms.openlocfilehash: 2ea3a470ab6b6d9cf3e7daeaf24cd82d0f7ac387
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47858493"
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228：不要发行未发布的资源格式
|||
|-|-|
|TypeName|DoNotShipUnreleasedResourceFormats|
|CheckId|CA2228|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 使用当前不支持的.NET framework 版本生成的资源文件。

## <a name="rule-description"></a>规则说明
 通过使用预发行版本的.NET Framework 生成的资源文件可能不是可由支持的.NET Framework 版本。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，生成使用.NET Frameworkk 的受支持的版本的资源。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。