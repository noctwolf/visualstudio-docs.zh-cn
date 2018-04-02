---
title: 示例 Excel 扩展：ActionFilter 类 | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 253a5a63ec31d09db3b38b6dea06e9ac85d8bfe7
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="sample-excel-extension-actionfilter-class"></a>示例 Excel 扩展：ActionFilter 类

此内部类扩展 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> 类，并表示 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 元素上的测试操作的筛选器。

## <a name="simple-properties"></a>简单属性

这些只读属性指定如何通过编码的 UI 测试框架来执行此测试操作筛选。 例如，<xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> 属性提供操作筛选器的名称。 其他属性可获取操作筛选器的 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A>、<xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>、由此测试操作筛选器筛选的测试操作的 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> 名称。 其他属性指示是否为 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> 以及测试操作是否为 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>。

## <a name="processrule-method"></a>ProcessRule 方法

此方法由编码的 UI 测试框架调用，并针对提供的 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack> 执行筛选器。 当堆栈中的下一个操作向单元格发送键击时，此特定重写将移除单元格的选择操作。 然后返回 `false`。

## <a name="private-methods"></a>私有方法

`IsLeftClick` 方法确定提供的操作是否表示单击鼠标左键。 `AreActionsOnSameExcelCell` 方法确定是否针对 Excel 中同一单元格执行所提供的两个操作。

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>
- [扩展编码的 UI 测试和操作录制以支持 Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
