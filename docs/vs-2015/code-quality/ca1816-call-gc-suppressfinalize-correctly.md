---
title: CA1816： 调用 GC。SuppressFinalize 正确 |Microsoft Docs
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
- CA1816
- DisposeMethodsShouldCallSuppressFinalize
helpviewer_keywords:
- DisposeMethodsShouldCallSuppressFinalize
- CA1816
ms.assetid: 47915fbb-103f-4333-b157-1da16bf49660
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e8c5123cc67dd6de273b9740a0a7dd4d7824eb10
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587741"
---
# <a name="ca1816-call-gcsuppressfinalize-correctly"></a>CA1816：正确调用 GC.SuppressFinalize
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA1816： 调用 GC。SuppressFinalize 正确](https://docs.microsoft.com/visualstudio/code-quality/ca1816-call-gc-suppressfinalize-correctly)。

|||
|-|-|
|TypeName|CallGCSuppressFinalizeCorrectly|
|CheckId|CA1816|
|类别|Microsoft。 用法|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

-   是的实现的方法<xref:System.IDisposable.Dispose%2A?displayProperty=fullName>不会调用<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>。

-   不是一种实现的方法<xref:System.IDisposable.Dispose%2A?displayProperty=fullName>调用<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>。

-   一个方法调用<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>，并将传递此 （我在 Visual Basic 中） 以外的其他内容。

## <a name="rule-description"></a>规则说明
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>方法可让用户随时可用于垃圾回收的对象之前释放资源。 如果<xref:System.IDisposable.Dispose%2A?displayProperty=fullName>方法调用时，它释放的对象的资源。 这使得无需终止。 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 应调用<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>使垃圾回收器不会调用对象的终结器。

 若要防止派生的类型有终结器无需重新实现 [System.IDisposable] (<!-- TODO: review code entity reference <xref:assetId:///System.IDisposable?qualifyHint=True&amp;autoUpgrade=False>  -->)，并调用它，未密封的类型而无需终结器应仍调用<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突：

 如果此方法的实现<xref:System.IDisposable.Dispose%2A>，添加对的调用<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>。

 如果此方法不是实现<xref:System.IDisposable.Dispose%2A>，请删除对<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>或将其移到该类型的<xref:System.IDisposable.Dispose%2A>实现。

 更改对所有调用<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>传递此 （我在 Visual Basic 中）。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果考虑使用仅禁止显示此规则的警告<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>来控制其他对象的生存期。 如果的实现不禁止显示此规则的警告<xref:System.IDisposable.Dispose%2A>不会调用<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>。 在此情况下，无法取消终止操作会降低性能，会有任何好处。

## <a name="example"></a>示例
 下面的示例显示了一种方法未正确调用<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>。

 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly/CS/FxCop.Usage.CallGCSuppressFinalizeCorrectly.cs#1)]
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly/VB/FxCop.Usage.CallGCSuppressFinalizeCorrectly.vb#1)]

## <a name="example"></a>示例
 下面的示例显示了一种方法的正确调用<xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>。

 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly2/CS/FxCop.Usage.CallGCSuppressFinalizeCorrectly2.cs#1)]
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.CallGCSuppressFinalizeCorrectly2/VB/FxCop.Usage.CallGCSuppressFinalizeCorrectly2.vb#1)]

## <a name="related-rules"></a>相关的规则
 [CA2215：Dispose 方法应调用基类 Dispose](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)

 [CA2216：可释放类型应声明终结器](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

## <a name="see-also"></a>请参阅
 [释放模式](http://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)



