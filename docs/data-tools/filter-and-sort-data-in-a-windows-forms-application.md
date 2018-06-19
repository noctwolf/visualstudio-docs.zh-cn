---
title: 在 Windows 窗体应用程序中的筛选器和排序数据
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
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: f8f693e0a370a05508753dc6881b99157c21ea47
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924964"
---
# <a name="filter-and-sort-data-in-a-windows-forms-application"></a>在 Windows 窗体应用程序中的筛选器和排序数据
通过设置筛选数据<xref:System.Windows.Forms.BindingSource.Filter%2A>属性设置为一个字符串表达式，返回的所需的记录。

 对数据进行排序通过设置<xref:System.Windows.Forms.BindingSource.Sort%2A>想要作为排序依据的列名称的属性; 追加`DESC`按降序排序，还是追加`ASC`按升序进行排序。

> [!NOTE]
>  如果你的应用程序不使用<xref:System.Windows.Forms.BindingSource>组件，你可以筛选和排序数据使用<xref:System.Data.DataView>对象。 有关详细信息，请参阅[Dataview](/dotnet/framework/data/adonet/dataset-datatable-dataview/dataviews)。

## <a name="to-filter-data-by-using-a-bindingsource-component"></a>通过使用 BindingSource 组件来筛选数据

-   设置<xref:System.Windows.Forms.BindingSource.Filter%2A>属性设置为你想要返回的表达式。 例如，以下代码将返回客户`CompanyName`以"B"开头：

     [!code-csharp[VbRaddataDisplaying#6](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_1.cs)]
     [!code-vb[VbRaddataDisplaying#6](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_1.vb)]

## <a name="to-sort-data-by-using-a-bindingsource-component"></a>若要通过使用 BindingSource 组件对数据排序

-   设置<xref:System.Windows.Forms.BindingSource.Sort%2A>到你想要作为排序依据的列的属性。 例如，下面的代码对客户进行排序上`CompanyName`降序排序的列：

     [!code-csharp[VbRaddataDisplaying#7](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_2.cs)]
     [!code-vb[VbRaddataDisplaying#7](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_2.vb)]

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)