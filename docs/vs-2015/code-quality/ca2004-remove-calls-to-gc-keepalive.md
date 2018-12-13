---
title: CA2004： 移除对 GC 的调用。KeepAlive |Microsoft Docs
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
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 944862f742e96ef061c3c425bb28c0addcb4fb4e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49829061"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004：移除对 GC.KeepAlive 的调用
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|类别|Microsoft.Reliability|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 类使用`SafeHandle`，但仍包含对调用`GC.KeepAlive`。

## <a name="rule-description"></a>规则说明
 如果将转换为`SafeHandle`使用情况，删除所有调用的`GC.KeepAlive`（对象）。 在这种情况下，类不必调用`GC.KeepAlive`，假定它们没有终结器但是依赖于`SafeHandle`它们完成 OS 句柄。  虽然保留对的调用中的成本`GC.KeepAlive`可能是由性能，感觉度量，可以忽略不计，调用`GC.KeepAlive`是必需或足以解决可能不再存在的问题使代码更加困难的生存期维护。

## <a name="how-to-fix-violations"></a>如何解决冲突
 删除对调用`GC.KeepAlive`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 仅当不从技术上讲正确，将转换为可取消显示此警告`SafeHandle`在类中的使用情况。



