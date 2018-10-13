---
title: 'CA1415: P 调用正确声明 |Microsoft Docs'
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
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b1edb0d85d4f00696f03dce0d8bfb6152d6a5042
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49251077"
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415：正确声明 P/Invoke
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|DeclarePInvokesCorrectly|
|CheckId|CA1415|
|类别|Microsoft.Interoperability|
|是否重大更改|无间断-如果 P/Invoke 声明参数不能程序集外可见。 是-如果 P/Invoke 声明该参数可以程序集外可见。|

## <a name="cause"></a>原因
 平台调用方法未正确声明。

## <a name="rule-description"></a>规则说明
 将平台调用方法访问非托管的代码与使用定义`Declare`中的关键字[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]或<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>。 目前，此规则查找针对平台调用目标有一个指针指向 OVERLAPPED 结构参数的 Win32 函数的方法声明和相应的托管的参数不是一个指向<xref:System.Threading.NativeOverlapped?displayProperty=fullName>结构。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请正确声明在平台调用方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 平台调用方法的规则冲突示例和满足该规则的以下示例所示。

 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DeclarePInvokes/cs/FxCop.Interoperability.DeclarePInvokes.cs#1)]

## <a name="see-also"></a>请参阅
 [与非托管代码交互操作](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



