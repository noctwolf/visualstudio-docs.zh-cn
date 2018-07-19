---
title: 创建参数化 TableAdapter 查询
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- TableAdapters, parameterized queries
- data [Visual Studio], searching data
- queries [Visual Studio], creating
- TableAdapters, searching data
- queries [Visual Studio], TableAdapters
ms.assetid: 104d1d19-b5a9-4071-b81e-1b3af08e9c7b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: fe77d3622e9c41d98ff89972e522bb25aae58b9d
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756004"
---
# <a name="create-parameterized-tableadapter-queries"></a>创建参数化 TableAdapter 查询
参数化查询将返回满足查询内的 WHERE 子句条件的数据。 例如，通过在返回客户列表的 SQL 语句的末尾添加 `WHERE City = @City`，可以参数化客户列表，使之只显示某个城市的客户。

 创建参数化的 TableAdapter 查询中**数据集设计器**。此外可以使用的 Windows 应用程序中创建它们**参数化数据源**命令**数据**菜单。 **参数化数据源**命令将创建可以在此输入参数值，并运行该查询在窗体上的控件。

> [!NOTE]
> 当构造参数化的查询，使用特定于你要对其编写代码的数据库的参数表示法。 例如，Access 和 OleDb 数据源使用问号“?”表示参数，所以 WHERE 子句将类似于：`WHERE City = ?`。

> [!NOTE]
> 对话框和菜单命令可能不同于中所述的帮助，具体取决于您现用的设置或正在使用的版本。 若要更改设置，请转到**工具**菜单，然后选择**导入和导出设置**。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)。

## <a name="create-a-parameterized-tableadapter-query"></a>创建参数化的 TableAdapter 查询

#### <a name="to-create-a-parameterized-query-in-the-dataset-designer"></a>在“数据集设计器”中创建参数化查询

-   将 WHERE 子句和所需参数添加到 SQL 语句中，以创建新的 TableAdapter。 有关详细信息，请参阅[创建和配置 Tableadapter](../data-tools/create-and-configure-tableadapters.md)。

     或

-   将 WHERE 子句和所需参数添加到 SQL 语句中，以向现有 TableAdapter 中添加查询。

#### <a name="to-create-a-parameterized-query-while-designing-a-data-bound-form"></a>在设计数据绑定窗体时创建参数化查询

1.  在窗体中选择已绑定到数据集的控件。 有关详细信息，请参阅[绑定 Windows 窗体控件添加到 Visual Studio 中的数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)。

2.  上**数据**菜单中，选择**添加查询**。

3.  完成**搜索标准生成器**对话框中，将 WHERE 子句和所需参数添加到 SQL 语句。

### <a name="to-add-a-query-to-an-existing-data-bound-form"></a>将查询添加到现有数据绑定窗体

1.  在“Windows 窗体设计器”中打开窗体。

2.  上**数据**菜单中，选择**添加查询**或**数据智能标记**。

    > [!NOTE]
    >  如果**添加查询**上不可用**数据**菜单中，选择要添加到参数化，显示的数据源，在窗体上的控件。 例如，如果窗体在 <xref:System.Windows.Forms.DataGridView> 控件中显示数据，则选择该控件。 如果窗体在各个控件中显示数据，则选择任意数据绑定控件。

3.  在中**选择数据源表**区域中，选择你想要添加参数化的表。

4.  中键入一个名称**新的查询名称**框如果要创建一个新的查询。

     或

     中选择一个查询**现有查询名称**框。

5.  在中**查询文本**框中，键入不带参数的查询。

6.  选择“确定”。

     一个控件用于输入参数和一个**负载**按钮添加到窗体中<xref:System.Windows.Forms.ToolStrip>控件。

#### <a name="querying-for-null-values"></a>查询的 null 值
TableAdapter 参数您想要的记录没有当前值的查询可以分配 null 值。 例如，考虑下面的查询具有`ShippedDate`中的参数及其`WHERE`子句：

 ```sql
SELECT CustomerID, OrderDate, ShippedDate
FROM Orders
WHERE (ShippedDate = @ShippedDate) OR (ShippedDate IS NULL)
```

 如果这是 TableAdapter 的查询，则可以查询尚未发运用下面的代码的所有订单：

 [!code-csharp[VbRaddataTableAdapters#8](../data-tools/codesnippet/CSharp/create-parameterized-tableadapter-queries_1.cs)]
 [!code-vb[VbRaddataTableAdapters#8](../data-tools/codesnippet/VisualBasic/create-parameterized-tableadapter-queries_1.vb)]

 若要启用查询能够接受 null 值：

1.  在中**数据集设计器**，选择需要接受 null 参数值的 TableAdapter 查询。

2.  在中**属性**窗口中，选择**参数**，然后单击省略号 (**...**) 按钮以打开**参数集合编辑器**。

3.  选择允许 null 值的参数，并设置**AllowDbNull**属性设置为`true`。

## <a name="see-also"></a>请参阅

- [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)