---
title: 如何： 删除数据库中的记录 |Microsoft Docs
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
- data [Visual Studio], saving
- records, deleting
- TableAdapter.Delete method
- databases, deleting records
- deleting data
- TableAdapter.Update method
- saving data
ms.assetid: d74d2130-9732-4648-abea-241059c4a372
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: aff5a67d54376488ccce2bca5dd67b84d6c73949
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49210179"
---
# <a name="how-to-delete-records-in-a-database"></a>如何：删除数据库中的记录
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

若要从数据库中删除记录，请使用`TableAdapter.Update`方法或`TableAdapter.Delete`方法。 或者，如果你的应用程序不使用 Tableadapter，可以使用命令对象从数据库删除记录 (例如， <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>)。  
  
 `TableAdapter.Update`当你的应用程序使用数据集来存储数据，而通常使用方法`TableAdapter.Delete`时你的应用程序使用对象来存储数据，通常使用方法。  
  
 如果不具有在 TableAdapter`Delete`方法，它表示任一 TableAdapter 配置为使用存储的过程或其`GenerateDBDirectMethods`属性设置为`false`。 尝试设置 TableAdapter`GenerateDBDirectMethods`属性设置为`true`中[数据集设计器](../data-tools/creating-and-editing-typed-datasets.md)然后将保存数据集来重新生成 TableAdapter。 如果仍不具有 TableAdapter`Delete`方法，则表可能没有提供足够的架构信息来区分各行 （例如，对表设置没有主键）。  
  
## <a name="delete-records-using-tableadapters"></a>使用 Tableadapter 删除记录  
 Tableadapter 提供不同的方式，具体取决于你的应用程序的要求数据库中删除记录。  
  
 如果你的应用程序使用数据集来存储数据可以从所需直接删除记录<xref:System.Data.DataTable>中<xref:System.Data.DataSet>，然后调用`TableAdapter.Update`方法。 `TableAdapter.Update`方法采用数据表中的任何更改，并将这些更改发送到数据库 （包括插入、 更新和删除记录）。  
  
#### <a name="to-delete-records-from-a-database-using-the-tableadapterupdate-method"></a>若要使用 TableAdapter.Update 方法从数据库删除记录  
  
-   删除记录所需<xref:System.Data.DataTable>通过删除<xref:System.Data.DataRow>表中的对象。 有关详细信息，请参阅[如何： 删除数据表中的行](http://msdn.microsoft.com/library/add481e5-08c7-4923-9276-f036ae29d31e)。 从删除行后<xref:System.Data.DataTable>，调用`TableAdapter.Update`方法。 您可以控制要更新通过将整个传入的数据量<xref:System.Data.DataSet>、 一个<xref:System.Data.DataTable>，数组<xref:System.Data.DataRow>s 或将单个<xref:System.Data.DataRow>。 下面的代码演示如何删除来自<xref:System.Data.DataTable>，然后调用`TableAdapter.Update`方法来更改进行通信并从数据库中删除行。 (本示例使用 Northwind 数据库`Region`表。)  
  
     [!code-csharp[VbRaddataSaving#20](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form5.cs#20)]
     [!code-vb[VbRaddataSaving#20](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form5.vb#20)]  
  
 如果你的应用程序使用对象来存储你的应用程序中的数据，可以使用 TableAdapter 的 DBDirect 方法直接从数据库中删除数据。 调用`Delete`方法从数据库中传递的参数值中删除记录。  
  
#### <a name="to-delete-records-from-a-database-using-the-tableadapterdelete-method"></a>若要使用 TableAdapter.Delete 方法从数据库删除记录  
  
-   调用 TableAdapter`Delete`方法，在值中的每个列将作为参数传递的`Delete`方法。 (本示例使用 Northwind 数据库`Region`表。)  
  
    > [!NOTE]
    >  如果没有可用的实例，实例化想要使用的 TableAdapter。  
  
     [!code-csharp[VbRaddataSaving#21](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#21)]
     [!code-vb[VbRaddataSaving#21](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#21)]  
  
## <a name="delete-records-using-command-objects"></a>使用命令对象删除记录  
 以下示例直接从使用命令对象的数据库中删除记录。 使用命令对象来执行命令和存储的过程的详细信息，请参阅[将数据提取到您的应用程序](../data-tools/fetching-data-into-your-application.md)。  
  
#### <a name="to-delete-records-from-a-database-using-command-objects"></a>若要使用命令对象从数据库删除记录  
  
-   创建新的命令对象，将设置其`Connection`， `CommandType`，和`CommandText`属性。 (本示例使用 Northwind 数据库`Region`表。)  
  
     [!code-csharp[VbRaddataSaving#22](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#22)]
     [!code-vb[VbRaddataSaving#22](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#22)]  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 必须有权访问尝试连接到数据库以及从所需的表中删除记录的权限。  
  
## <a name="see-also"></a>请参阅  
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)   
 [将新记录插入数据库](../data-tools/insert-new-records-into-a-database.md)   
 [如何： 更新数据库中的记录](../data-tools/how-to-update-records-in-a-database.md)   
 [将数据从对象保存到数据库](../data-tools/save-data-from-an-object-to-a-database.md)   
 [在 Visual Studio 中的数据应用程序的概述](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)