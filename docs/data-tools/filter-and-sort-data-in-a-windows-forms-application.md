---
title: 在 Windows 窗体应用程序中对数据进行筛选和排序
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- row states, filtering
- data views, sorting
- row version, filtering
- row states
- data views, filtering
- sorting datasets, using data views
- dataset filtering, using data views
ms.assetid: f4f100f1-776d-46dc-b2fd-5b35b98d9561
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: ed61f8e1ee864cc07132ae003dc0238884d370ba
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54997918"
---
# <a name="filter-and-sort-data-in-a-windows-forms-application"></a>在 Windows 窗体应用程序中对数据进行筛选和排序

设置筛选数据<xref:System.Windows.Forms.BindingSource.Filter%2A>属性设置为一个字符串表达式，返回所需的记录。

对数据进行排序通过设置<xref:System.Windows.Forms.BindingSource.Sort%2A>属性设置为列名称在其进行排序; 追加`DESC`按降序排序，还是追加`ASC`以按升序排序。

> [!NOTE]
> 如果你的应用程序不使用<xref:System.Windows.Forms.BindingSource>组件，您可以筛选和排序数据使用<xref:System.Data.DataView>对象。 有关详细信息，请参阅[Dataview](/dotnet/framework/data/adonet/dataset-datatable-dataview/dataviews)。

## <a name="to-filter-data-by-using-a-bindingsource-component"></a>通过使用 BindingSource 组件来筛选数据

-   设置<xref:System.Windows.Forms.BindingSource.Filter%2A>属性设置为你想要返回的表达式。 例如，以下代码将返回与客户`CompanyName`"B"开头的：

     [!code-csharp[VbRaddataDisplaying#6](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_1.cs)]
     [!code-vb[VbRaddataDisplaying#6](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_1.vb)]

## <a name="to-sort-data-by-using-a-bindingsource-component"></a>若要使用 BindingSource 组件对数据进行排序

-   设置<xref:System.Windows.Forms.BindingSource.Sort%2A>属性设置为你想要按其排序的列。 例如，下面的代码对客户排序上`CompanyName`降序排序的列：

     [!code-csharp[VbRaddataDisplaying#7](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_2.cs)]
     [!code-vb[VbRaddataDisplaying#7](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_2.vb)]

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)