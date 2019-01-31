---
title: 示例 Excel 扩展：ActionFilter 类 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: c69fe3c7-f797-4e90-b21c-f2cc4dddf152
caps.latest.revision: 13
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 86c1dda46ed0e62649a576a12c9f9e48561ec891
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767839"
---
# <a name="sample-excel-extension-actionfilter-class"></a>示例 Excel 扩展：ActionFilter 类
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

此内部类扩展 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> 类，并表示 [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 元素上的测试操作的筛选器。  
  
## <a name="simple-properties"></a>简单属性  
 通过这些只读属性，开发人员可以指定如何通过编码的 UI 测试框架来执行此测试操作筛选器。 例如，<xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> 属性提供操作筛选器的名称。 其他属性可获取操作筛选器的 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A>、<xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>、由此测试操作筛选器筛选的测试操作的 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> 名称。 其他属性指示是否为 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> 以及测试操作是否为 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>。  
  
## <a name="processrule-method"></a>ProcessRule 方法  
 此方法由编码的 UI 测试框架调用，并针对提供的 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack> 执行筛选器。 当堆栈中的下一个操作向单元格发送键击时，此特定重写将移除单元格的选择操作。 然后返回 `false`。  
  
## <a name="private-methods"></a>私有方法  
 `IsLeftClick` 方法确定提供的操作是否表示单击鼠标左键。 `AreActionsOnSameExcelCell` 方法确定是否针对 Excel 中同一单元格执行所提供的两个操作。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>   
 [扩展编码的 UI 测试和操作录制以支持 Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
