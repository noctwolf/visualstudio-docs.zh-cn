---
title: 如何： 用数据填充数据集 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- TableAdapter.GetData
- TableAdapter.Fill
- datasets [Visual Basic], filling
- DataTable objects, loading
- data [Visual Basic], loading into datasets
ms.assetid: 7ab436d4-54ba-4621-902f-3f193279e18c
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: c2bba5c7bcdf1453129c6c3677e750c0e5599bac
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479486"
---
# <a name="how-to-fill-a-dataset-with-data"></a>如何： 用数据填充数据集
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

短语"使用数据填充数据集"是指将数据加载到单个<xref:System.Data.DataTable>构成数据集对象。 通过执行 TableAdapter 查询或通过执行数据适配器填充数据的表 (例如， <xref:System.Data.SqlClient.SqlDataAdapter>) 命令。  
  
 是否应该使用 Tableadapter 或数据适配器取决于如何创建数据集。 如果使用中的设计工具[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]，如[数据源配置向导](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)，你的数据集包含 Tableadapter。 Tableadapter 的详细信息，请参阅[TableAdapter 概述](../data-tools/tableadapter-overview.md)。 如果以编程方式创建数据集，通常需要创建数据适配器将数据加载到数据表。  
  
> [!NOTE]
>  当将某些项从[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)拖动到窗体的代码以便用数据填充数据表自动添加到`Form_Load`事件处理程序。 若要查看用于填充特定表的确切语法在代码编辑器中打开窗体。 如果您不想要在窗体加载时填充表，可以将此代码移到其他的方法，或将它完全移除。  
  
## <a name="filling-a-dataset-using-a-tableadapter"></a>填充数据集使用 TableAdapter  
 可以将数据加载到数据集中数据表的 TableAdapter 上调用的查询。 传递<xref:System.Data.DataTable>想要填充到 TableAdapter 查询。 如果您的查询采用参数，将这些参数传递给该方法也。 如果数据集包含多个表，您应具有的每个表单独 Tableadapter，并因此必须填充每个表单独。  
  
> [!NOTE]
>  默认情况下，每次执行 TableAdapter 查询，已被清除表中的数据之前加载到表的查询的结果。 可以保留现有数据的表中并通过设置 TableAdapter 的附加结果`ClearBeforeFill`属性设置为`false`。  
  
#### <a name="to-fill-a-dataset-with-data-using-a-tableadapter"></a>若要使用 TableAdapter 与数据填充数据集  
  
1.  打开窗体或组件中的**代码编辑器**。  
  
2.  需要加载包含数据的数据表在应用程序中的任意位置添加代码。 如果您的查询不带参数，则传入<xref:System.Data.DataTable>想要填充。 代码应类似于下面：  
  
     [!code-csharp[VbRaddataFillingAndExecuting#4](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#4)]
     [!code-vb[VbRaddataFillingAndExecuting#4](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#4)]  
  
3.  如果您的查询采用参数，则传入<xref:System.Data.DataTable>要填充和查询所需的参数。 具体取决于在查询中的实际参数，该代码将类似于下面的示例：  
  
     [!code-csharp[VbRaddataFillingAndExecuting#5](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#5)]
     [!code-vb[VbRaddataFillingAndExecuting#5](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#5)]  
  
## <a name="filling-a-dataset-using-a-dataadapter"></a>填充数据集使用 DataAdapter  
 调用数据适配器的`Fill`方法。 这会导致适配器来执行 SQL 语句或存储的过程中引用其`SelectCommand`属性并将结果放入的表中数据集。 如果数据集包含多个表，您都必须具有单独的数据适配器为每个表，并因此必须填充每个表单独。  
  
#### <a name="to-fill-a-dataset-with-data-using-a-dataadapter"></a>若要使用数据使用 DataAdapter 填充数据集  
  
-   调用<xref:System.Data.Common.DataAdapter.Fill%2A>方法<xref:System.Data.Common.DataAdapter>，并传入<xref:System.Data.DataSet>或<xref:System.Data.DataTable>若要将数据加载到。 例如：  
  
     [!code-csharp[VbRaddataFillingAndExecuting#6](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#6)]
     [!code-vb[VbRaddataFillingAndExecuting#6](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#6)]  
  
     通常应提供的名称<xref:System.Data.DataTable>若要将数据加载到。 如果传递的名称<xref:System.Data.DataSet>而不是特定数据表<xref:System.Data.DataTable>名为`Table1`添加到数据集并加载的结果与数据库 (而不是加载中的现有数据<xref:System.Data.DataTable>在数据集中)。 有关详细信息，请参阅[填充数据集从 DataAdapter](http://msdn.microsoft.com/library/3fa0ac7d-e266-4954-bfac-3fbe2f913153)。  
  
## <a name="see-also"></a>请参阅  
 [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)