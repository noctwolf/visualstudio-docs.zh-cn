---
title: TableAdapter 概述 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vbData.Microsoft.VSDesigner.DataSource.DataAccessor
- vbdata.Microsoft.VSDesigner.DataSource.DataAccessor
- TableAdapter
- vs.data.TableAdapter
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], table adapters
- TableAdapters, queries
- data [Visual Studio], TableAdapters
- query data in Visual Studio
- TableAdapter.GetData
- TableAdapter.Fill
- data [Visual Studio], datasets
- TableAdapters
- table adapters
ms.assetid: a87c46a0-52ab-432a-a864-9ba55069f9eb
caps.latest.revision: 40
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: fb5ebcdaa1bebe67c2fb8e378c7345467dd10b78
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269043"
---
# <a name="tableadapter-overview"></a>TableAdapter 概述
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tableadapter 是连接到数据库、 执行查询或存储的过程，并使用返回的数据填充其 DataTable 的设计器生成组件。 Tableadapter 还用于从应用程序与数据库发送更新后的数据。 可以有任意数量的查询，因为你想在 TableAdapter 上，只要它们符合的数据返回到 TableAdapter 与之关联的表的架构。 下图显示了 Tableadapter 如何与数据库和内存中的其他对象进行交互：  
  
 ![客户端应用程序中的数据流](../data-tools/media/clientdatadiagram.gif "ClientDataDiagram")  
  
 Tableadapter 的设计时**数据集设计器**，生成的 TableAdapter 类不会生成嵌套的类作为<xref:System.Data.DataSet>。 它们位于特定于每个数据集的单独命名空间中。 例如，如果您有一个名为的数据集`NorthwindDataSet`，与关联的 Tableadapter<xref:System.Data.DataTable>中的 s`NorthwindDataSet`会采用`NorthwindDataSetTableAdapters`命名空间。 若要以编程方式访问特定的 TableAdapter，您必须声明 TableAdapter 的新实例。 例如：  
  
 [!code-csharp[VbRaddataTableAdapters#7](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataTableAdapters/CS/Class1.cs#7)]
 [!code-vb[VbRaddataTableAdapters#7](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataTableAdapters/VB/Class1.vb#7)]  
  
## <a name="associated-datatable-schema"></a>关联的 DataTable 架构  
 当创建 TableAdapter、 初始查询或存储的过程用于定义 TableAdapter 的架构的关联<xref:System.Data.DataTable>。 通过调用 TableAdapter 的执行此初始查询或存储的过程`Fill`方法 (它将填充 TableAdapter 的关联<xref:System.Data.DataTable>)。 TableAdapter 的主查询所做的任何更改都反映在关联的数据的表的架构。 例如，从主查询中删除列的列从表中删除关联的数据。 如果在 TableAdapter 上的任何其他查询中使用 SQL 语句返回不在主查询中的列，然后在设计器将尝试同步主查询和任何其他查询之间的列更改。 有关详细信息，请参阅[如何： 编辑 Tableadapter](http://msdn.microsoft.com/library/ca178745-e35a-45f1-a395-23cddfd8f855)。  
  
## <a name="tableadapter-update-commands"></a>TableAdapter 更新命令  
 TableAdapter 的更新功能是依赖于基于 TableAdapter 向导中提供的主查询可以提供了多少信息。 例如，配置为提取多个表 （联接） 中的值、 标量值、 视图或聚合函数的结果的 Tableadapter 最初创建时不能够将更新发送回基础数据库。 但是，可以配置的 INSERT、 UPDATE 和 DELETE 命令中手动**属性**窗口。  
  
## <a name="tableadapter-queries"></a>TableAdapter 查询  
 ![使用多个查询的 TableAdapter](../data-tools/media/tableadapter.gif "TableAdapter")  
  
 Tableadapter 可包含多个查询以填充其关联的数据的表。 可以定义任意多个查询的 TableAdapter，因为应用程序需要，只要每个查询返回到其关联的数据的表相同的架构数据的架构。 这样，加载满足不同条件的数据。 例如，如果你的应用程序包含的客户表，可以创建其名称以某些字母开头，每个客户使用填充表的查询和填充表与位于相同的州的所有客户的另一个查询。 以填充`Customers`表中可以创建某一给定状态的客户`FillByState`采用的州值参数的查询： `SELECT * FROM Customers WHERE State = @State`。 通过调用执行查询`FillByState`方法并传入参数值如下： `CustomerTableAdapter.FillByState("WA")`。 有关详细信息，请参阅[如何： 创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)。  
  
 除了返回的 TableAdapter 的数据表的架构相同的数据的查询，可以添加返回标量 （单个） 值的查询。 例如，创建一个查询返回的客户计数 (`SELECT Count(*) From Customers`) 对有效`CustomersTableAdapter`即使返回的数据不符合表的架构。  
  
## <a name="clearbeforefill-property"></a>ClearBeforeFill 属性  
 默认情况下，每次执行查询以填充 TableAdapter 的数据表，清除数据，并仅在查询结果加载到表。 设置 TableAdapter`ClearBeforeFill`属性设置为`false`如果想要添加或合并到数据表中的现有数据从查询返回的数据。 无论是否清除了数据，都需要显式将更新发送回数据库中，如果所需的。 因此请务必保存对表中的数据填充表的另一个查询在执行之前做任何更改。 有关详细信息，请参阅[使用 TableAdapter 更新数据](../data-tools/update-data-by-using-a-tableadapter.md)。  
  
## <a name="tableadapter-inheritance"></a>TableAdapter 继承  
 Tableadapter 扩展标准数据适配器的功能通过封装一个已配置<xref:System.Data.Common.DataAdapter>。 默认情况下，TableAdapter 继承<xref:System.ComponentModel.Component>并且不能强制转换为<xref:System.Data.Common.DataAdapter>类。 强制转换到 TableAdapter<xref:System.Data.Common.DataAdapter>导致<xref:System.InvalidCastException>。 若要更改的 TableAdapter 的基类，可以键入派生的类<xref:System.ComponentModel.Component>中**基类**属性中对 TableAdapter**数据集设计器**。  
  
## <a name="tableadapter-methods-and-properties"></a>TableAdapter 方法和属性  
 TableAdapter 类不属于[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]，并且这种情况下你不能查找其文档中或**对象浏览器**。 在设计时，当你使用前面所述的向导之一创建。 在创建时分配给 TableAdapter 的名称基于你正在使用的表的名称。 例如，当创建 TableAdapter 基于一个名为数据库中的表`Orders`，将命名为 TableAdapter `OrdersTableAdapter`。 可以使用更改类名称的 TableAdapter**名称**属性中的**数据集设计器**。  
  
 以下是常用的方法和 Tableadapter 的属性：  
  
|成员|描述|  
|------------|-----------------|  
|`TableAdapter.Fill`|该表中填充 TableAdapter 的关联的数据的 TableAdapter 的 SELECT 命令的结果。 有关详细信息，请参阅[如何： 用数据填充数据集](../data-tools/how-to-fill-a-dataset-with-data.md)。|  
|`TableAdapter.Update`|将更改发送回数据库，并返回一个整数，表示更新影响的行数。 有关详细信息，请参阅[使用 TableAdapter 更新数据](../data-tools/update-data-by-using-a-tableadapter.md)。|  
|`TableAdapter.GetData`|返回一个新<xref:System.Data.DataTable>已填满数据。|  
|`TableAdapter.Insert`|在数据表中创建一个新行。 有关详细信息，请参阅[如何： 向数据表中添加行](http://msdn.microsoft.com/library/78ebbb43-c402-49cf-81da-0715289487bf)。|  
|`TableAdapter.ClearBeforeFill`|确定数据表之前调用其中一个将被清空`Fill`方法。|  
  
## <a name="tableadapter-update-method"></a>TableAdapter 更新方法  
 Tableadapter 使用数据命令来读取和写入数据库中。 TableAdapter 的初始`Fill`（主） 查询用于创建关联的数据的表的架构用作的基础，以及`InsertCommand`， `UpdateCommand`，和`DeleteCommand`与关联的命令`TableAdapter.Update`方法。 这意味着，调用 TableAdapter`Update`方法执行的语句时创建 TableAdapter 的最初配置，而不是一个其他查询添加与**TableAdapter 查询配置向导**.  
  
 当使用 TableAdapter 时，它将有效地执行与你通常会执行的命令相同的操作。 例如，当调用适配器的`Fill`方法中，适配器将执行中的数据命令及其`SelectCommand`属性，并使用数据读取器 (例如， <xref:System.Data.SqlClient.SqlDataReader>) 要加载的结果集到数据表。 同样，当调用该适配器`Update`方法中，执行相应的命令 (在`UpdateCommand`， `InsertCommand`，和`DeleteCommand`属性) 为每个更改数据表中的记录。  
  
> [!NOTE]
>  如果没有足够的信息在主查询中， `InsertCommand`， `UpdateCommand`，和`DeleteCommand`生成 TableAdapter 时默认情况下创建命令。 如果 TableAdapter 的主查询不只是一个单表 SELECT 语句，就可以在设计器将不能生成`InsertCommand`， `UpdateCommand`，和`DeleteCommand`。 如果不会生成这些命令，在执行时，可能会收到错误`TableAdapter.Update`方法。  
  
## <a name="tableadapter-generatedbdirectmethods"></a>TableAdapter GenerateDbDirectMethods  
 除了`InsertCommand`， `UpdateCommand`，和`DeleteCommand`，可以直接对数据库执行的方法创建 Tableadapter。 这些方法 (`TableAdapter.Insert`， `TableAdapter.Update`，和`TableAdapter.Delete`) 可以调用直接以操作数据库中的数据。 这意味着您可以从您的代码而不是调用 TableAdapter.Update 处理插入、 更新和删除操作处于挂起状态调用这些单个方法的相关联的数据表。  
  
 如果您不想要创建以下直接方法，设置 TableAdapter **GenerateDbDirectMethods**属性设置为`false`(在**属性**窗口)。 添加到 TableAdapter 的其他查询均为独立查询 — 它们不会产生这些方法。  
  
## <a name="tableadapter-support-for-nullable-types"></a>TableAdapter 支持可以为 Null 的类型  
 Tableadapter 支持可以为 null 的类型`Nullable(Of T)`和`T?`。 在 Visual Basic 中为 null 的类型的详细信息，请参阅[可以为 Null 的值类型](http://msdn.microsoft.com/library/9ac3b602-6f96-4e6d-96f7-cd4e81c468a6)。 C# 中可以为 null 类型的详细信息，请参阅[使用可以为 Null 的类型](http://msdn.microsoft.com/library/0bacbe72-ce15-4b14-83e1-9c14e6380c28)。  
  
## <a name="see-also"></a>请参阅  
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [如何：连接到数据库中的数据](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [演练： 连接到数据库 （Windows 窗体） 中的数据](http://msdn.microsoft.com/library/02d39aa6-8993-4602-be13-a13536af3d1c)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)