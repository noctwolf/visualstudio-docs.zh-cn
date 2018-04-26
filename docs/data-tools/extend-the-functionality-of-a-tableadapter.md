---
title: 扩展 TableAdapter 的功能
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- data [Visual Studio], extending TableAdapters
- TableAdapters, adding functionality
ms.assetid: 418249c8-c7f3-47ef-a94c-744cb6fe6aaf
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 9b5884ff140097010c90fbf2208fecd95980f2fe
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="extend-the-functionality-of-a-tableadapter"></a>扩展 TableAdapter 的功能
可以通过将代码添加到 TableAdapter 的分部类文件来扩展 TableAdapter 的功能。

 对在 TableAdapter 进行任何更改时，将重新定义 TableAdapter 的代码**数据集设计器**，或当向导修改 TableAdapter 的配置。 若要防止在 TableAdapter 的重新生成过程正在删除你的代码，请将代码添加到 TableAdapter 的分部类文件。

 分部类允许为特定类划分到多个物理文件的代码。 有关详细信息，请参阅[部分](/dotnet/visual-basic/language-reference/modifiers/partial)或[分部 （类型）](/dotnet/csharp/language-reference/keywords/partial-type)。

## <a name="locate-tableadapters-in-code"></a>在代码中找到 Tableadapter
 虽然 Tableadapter 的设计也考虑了**数据集设计器**，生成的 TableAdapter 类就不是嵌套的类的<xref:System.Data.DataSet>。 Tableadapter 位于基于 TableAdapter 的关联数据集的名称的命名空间中。 例如，如果你的应用程序包含名为数据集`HRDataSet`，将位于 Tableadapter`HRDataSetTableAdapters`命名空间。 (命名约定遵循以下模式： *DatasetName* + `TableAdapters`)。

 下面的示例假定名为 TableAdapter`CustomersTableAdapter`在项目中使用`NorthwindDataSet`。

#### <a name="to-create-a-partial-class-for-a-tableadapter"></a>若要为 TableAdapter 创建分部类

1.  将新类添加到你的项目中，通过转到**项目**菜单并选择**添加类**。

2.  将此类命名为 `CustomersTableAdapterExtended`。

3.  选择**添加**。

4.  将代码替换正确的命名空间和为你的项目的分部类名称如下所示：

     [!code-csharp[VbRaddataTableAdapters#2](../data-tools/codesnippet/CSharp/extend-the-functionality-of-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataTableAdapters#2](../data-tools/codesnippet/VisualBasic/extend-the-functionality-of-a-tableadapter_1.vb)]

## <a name="see-also"></a>请参阅

- [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)