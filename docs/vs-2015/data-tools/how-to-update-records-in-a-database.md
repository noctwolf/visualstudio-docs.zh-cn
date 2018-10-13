---
title: 如何： 更新数据库中的记录 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
- records, updating
- data [Visual Studio], saving
- records, editing
- databases, updating
- TableAdapter.Update method
ms.assetid: cdc8a8e4-a5fa-40dd-9221-97b8571d802a
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: b880353b227eae86c7c35f274271fb404b62ede0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49199507"
---
# <a name="how-to-update-records-in-a-database"></a>如何：更新数据库中的记录
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可以使用`TableAdapter.Update`到数据库中的更新 （编辑） 记录的方法。 `TableAdapter.Update`方法提供了多个重载，执行不同操作，具体取决于传入的参数。 请务必了解调用这些不同的方法签名的结果。  
  
> [!NOTE]
>  如果你的应用程序不使用 Tableadapter，则可以使用命令对象在数据库中更新记录 (例如， <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>)。 命令对象使用更新数据的详细信息，请参阅下面的"使用命令对象的更新记录"。  
  
 下表介绍的各种行为`TableAdapter.Update`方法：  
  
|方法|描述|  
|------------|-----------------|  
|`TableAdapter.Update(DataTable)`|尝试保存中的所有更改<xref:System.Data.DataTable>到数据库。 （这包括删除所有表，将行插入到表中，添加和更新表中已更改的行中删除的行。）|  
|`TableAdapter.Update(DataSet)`|虽然此参数采用一个数据集，关联的 TableAdapter 尝试将所有更改都保存在 TableAdapter<xref:System.Data.DataTable>到数据库。 （这包括删除所有表，将行插入表中添加和更新表中已更改的行中删除的行。）**注意：** TableAdapter 的关联<xref:System.Data.DataTable>是<xref:System.Data.DataTable>最初配置 TableAdapter 时创建。|  
|`TableAdapter.Update(DataRow)`|尝试将更改保存在所指示<xref:System.Data.DataRow>到数据库。|  
|`TableAdapter.Update(DataRows())`|尝试保存的数组中的任意行中的更改<xref:System.Data.DataRow>的数据库。|  
|`TableAdapter.Update("new column values", "original column values")`|尝试保存的原始列值标识的单个行中的更改。|  
  
 通常使用`TableAdapter.Update`方法采用<xref:System.Data.DataSet>， <xref:System.Data.DataTable>，或<xref:System.Data.DataRow>(s) 时你的应用程序使用数据集以独占方式来存储数据。  
  
 通常使用`TableAdapter.Update`取列值时你的应用程序使用对象来存储数据的方法。  
  
 如果不具有在 TableAdapter`Update`采用列的值，则意味着任一 TableAdapter 配置为使用存储的过程的方法或其`GenerateDBDirectMethods`属性设置为`false`。 尝试设置 TableAdapter`GenerateDBDirectMethods`属性设置为`true`中[数据集设计器](../data-tools/creating-and-editing-typed-datasets.md)然后将保存数据集来重新生成 TableAdapter。 如果仍不具有 TableAdapter`Update`方法可能采用列的值，则表不提供足够的架构信息来区分各行 （例如，对表设置没有主键）。  
  
## <a name="update-existing-records-using-tableadapters"></a>更新使用 Tableadapter 的现有记录  
 Tableadapter 提供不同的方式，具体取决于你的应用程序的要求数据库中更新记录。  
  
 如果你的应用程序使用数据集来存储数据，则只需更新中的所需的记录<xref:System.Data.DataTable>，然后调用`TableAdapter.Update`方法并传入<xref:System.Data.DataSet>， <xref:System.Data.DataTable>， <xref:System.Data.DataRow>，或数组<xref:System.Data.DataRow>s。 上表描述了不同`Update`方法。  
  
#### <a name="to-update-records-in-a-database-with-the-tableadapterupdate-method-that-takes-dataset-datatable-datarow-or-datarows"></a>若要使用采用数据集、 数据表、 DataRow，或者 DataRows() TableAdapter.Update 方法更新数据库中的记录  
  
1.  编辑记录中的所需<xref:System.Data.DataTable>通过直接编辑<xref:System.Data.DataRow>中<xref:System.Data.DataTable>。 有关详细信息，请参阅[如何： 编辑数据表中的行](http://msdn.microsoft.com/library/d5eea200-9bfa-4956-bf7c-08dd6fb6663c)。  
  
2.  对行中进行编辑后<xref:System.Data.DataTable>，调用`TableAdapter.Update`方法。 您可以控制要更新通过传入一个完整的数据量<xref:System.Data.DataSet>、 一个<xref:System.Data.DataTable>，数组<xref:System.Data.DataRow>s 或将单个<xref:System.Data.DataRow>。  
  
     下面的代码演示如何编辑中的记录<xref:System.Data.DataTable>，然后调用`TableAdapter.Update`方法以将所做的更改保存到数据库。 （此示例使用 Northwind 数据库区域表）。  
  
     [!code-csharp[VbRaddataSaving#17](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form5.cs#17)]
     [!code-vb[VbRaddataSaving#17](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form5.vb#17)]  
  
 如果应用程序使用对象来存储你的应用程序中的数据，则可以使用 TableAdapter 的`DBDirect`方法将数据从您的对象直接发送到数据库。 这些方法，可将每列的单个值作为方法参数传递。 调用此方法使用的列的值传递给该方法更新数据库中的现有记录。  
  
 以下过程使用 Northwind`Region`作为示例表。  
  
#### <a name="to-update-records-in-a-database-using-the-tableadapterupdate-method-that-takes-column-values"></a>若要使用的 TableAdapter.Update 方法带有列的值的数据库中更新记录  
  
-   调用 TableAdapter 的`Update`方法，在新的和原始值中的每个列将作为参数传递。  
  
    > [!NOTE]
    >  如果没有可用的实例，实例化想要使用的 TableAdapter。  
  
     [!code-csharp[VbRaddataSaving#18](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#18)]
     [!code-vb[VbRaddataSaving#18](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#18)]  
  
## <a name="update-records-using-command-objects"></a>使用命令对象的更新记录  
 以下示例将更新直接在使用命令对象的数据库中的现有记录。 使用命令对象来执行命令和存储的过程的详细信息，请参阅[将数据提取到您的应用程序](../data-tools/fetching-data-into-your-application.md)。  
  
 以下过程使用 Northwind`Region`作为示例表。  
  
#### <a name="to-update-existing-records-in-a-database-using-command-objects"></a>若要更新使用命令对象的数据库中的现有记录  
  
-   创建新的命令对象;设置其`Connection`， `CommandType`，和`CommandText`属性，然后打开的连接并执行命令。  
  
     [!code-csharp[VbRaddataSaving#19](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#19)]
     [!code-vb[VbRaddataSaving#19](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#19)]  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 必须有权访问尝试连接到数据库以及更新所需的表中的记录的权限。  
  
## <a name="see-also"></a>请参阅  
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)   
 [如何： 删除数据库中的记录](../data-tools/how-to-delete-records-in-a-database.md)   
 [将新记录插入数据库](../data-tools/insert-new-records-into-a-database.md)   
 [将数据从对象保存到数据库](../data-tools/save-data-from-an-object-to-a-database.md)   
 [在 Visual Studio 中的数据应用程序的概述](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)