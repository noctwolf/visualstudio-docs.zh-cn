---
title: CA2220： 终结器应调用基类的终结器 |Microsoft Docs
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
- CA2220
- FinalizersShouldCallBaseClassFinalizer
helpviewer_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0489cce326dc74f790a5eb43caf464792733ec67
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49223933"
---
# <a name="ca2220-finalizers-should-call-base-class-finalizer"></a>CA2220：终结器应调用基类的终结器
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|FinalizersShouldCallBaseClassFinalizer|
|CheckId|CA2220|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 重写的类型<xref:System.Object.Finalize%2A?displayProperty=fullName>不会调用<xref:System.Object.Finalize%2A>中其基本类的方法。

## <a name="rule-description"></a>规则说明
 终止必须通过继承层次结构传播。 若要确保这一点，类型必须调用其基类<xref:System.Object.Finalize%2A>方法从其自身<xref:System.Object.Finalize%2A>方法。 C# 编译器会自动添加到基类的终结器调用。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请调用基类型<xref:System.Object.Finalize%2A>方法从你<xref:System.Object.Finalize%2A>方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 面向公共语言运行时的某些编译器对基类型的终结器的调用插入到 Microsoft 中间语言 (MSIL)。 如果报告此规则的警告，则编译器不会插入调用，并必须将其添加到你的代码。

## <a name="example"></a>示例
 下面的 Visual Basic 示例显示了一种类型`TypeB`的正确调用<xref:System.Object.Finalize%2A>中其基本类的方法。

 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposableBaseCalled/vb/FxCop.Usage.IDisposableBaseCalled.vb#1)]

## <a name="see-also"></a>请参阅
 [释放模式](http://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)



