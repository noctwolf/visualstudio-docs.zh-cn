---
title: 如何： 执行不返回值的存储的过程 |Microsoft Docs
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
- ExecuteNonQuery method
- stored procedures, creating
- stored procedures, executing
ms.assetid: 8a929e96-2cf5-43a5-b5b7-c0a5a397bbc5
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 0a9c80f37e5d569fd3a257f678256f01aba44925
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483381"
---
# <a name="how-to-execute-a-stored-procedure-that-returns-no-value"></a>如何：执行不返回值的存储过程
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

若要执行不返回值的存储的过程，可以运行 TableAdapter 查询配置为运行存储的过程 (例如， `CustomersTableAdapter.UpdateTableData(CustomersDataTable)`)。  
  
 如果你的应用程序不使用 Tableadapter，调用`ExecuteNonQuery`上设置的命令对象的方法及其`CommandType`属性设置为<xref:System.Data.CommandType>。 ("命令对象"指与特定的命令[.NET Framework 数据提供程序](http://msdn.microsoft.com/library/03a9fc62-2d24-491a-9fe6-d6bdb6dcb131)使用你的应用程序。 例如，如果你的应用程序使用适用于 SQL Server 的.NET Framework 数据提供程序，则命令对象应<xref:System.Data.SqlClient.SqlCommand>。)  
  
 以下示例演示如何执行存储的过程不返回值的使用任一 Tableadapter 从数据库或命令对象。 使用 Tableadapter 和命令进行查询的详细信息，请参阅[使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="executing-stored-procedures-that-return-no-values-using-a-tableadapter"></a>执行不返回值使用 TableAdapter 的存储的过程  
 此示例演示如何创建 TableAdapter 查询使用[编辑 Tableadapter](../data-tools/editing-tableadapters.md)，然后它提供有关如何声明 TableAdapter 的实例和执行查询信息。  
  
#### <a name="to-create-a-stored-procedure-that-returns-no-value-using-a-tableadapter"></a>若要创建不返回值使用 TableAdapter 的存储的过程  
  
1.  打开中的数据集**数据集设计器**。 有关详细信息，请参阅[如何： 在数据集设计器中打开数据集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
2.  如果你还没有一个创建的 TableAdapter。 创建 Tableadapter 的详细信息，请参阅[创建和配置 Tableadapter](../data-tools/create-and-configure-tableadapters.md)。  
  
3.  如果使用存储的过程不返回值在 TableAdapter 上已有一个查询，请跳到下一个过程，""声明的 TableAdapter 实例并执行查询。 否则，继续执行步骤 4，以创建新的查询不返回值。  
  
4.  右键单击你想，TableAdapter 并使用快捷菜单添加查询。  
  
     **TableAdapter 查询配置向导**随即打开。  
  
5.  选择**使用现有的存储的过程**，然后单击**下一步**。  
  
6.  从下拉列表中，选择存储的过程，然后单击**下一步**。  
  
7.  选择选项以返回**没有值**，然后单击**下一步**。  
  
8.  提供查询的名称。  
  
9. 单击**下一步**，或**完成**以完成向导; 将查询添加到 TableAdapter。  
  
10. 生成你的项目。  
  
#### <a name="to-declare-an-instance-of-the-tableadapter-and-execute-the-query"></a>若要声明的 TableAdapter 实例并执行查询  
  
1.  声明包含你想要执行的查询的 TableAdapter 的实例。  
  
    -   若要创建使用设计时工具的实例，将想要从 TableAdapter**工具箱**。 (现在在项目中的组件中将出现**工具箱**标题下的项目名称相匹配。)如果未出现在 TableAdapter**工具箱**，则需要生成项目。  
  
         或  
  
    -   若要在代码中创建一个实例，将的名称替换为以下代码在<xref:System.Data.DataSet>和 TableAdapter。  
  
         `Dim tableAdapter As New DataSetTableAdapters.TableAdapter`  
  
        > [!NOTE]
        >  不在其关联的数据集类中使用实际位于 Tableadapter。 每个数据集具有自己的命名空间中的相应集合的 Tableadapter。 例如，如果您有一个名为的数据集`SalesDataSet`，则不会有`SalesDataSetTableAdapters`包含其 Tableadapter 的命名空间。  
  
2.  在代码中调用任何其他方法的方式，请调用您的查询。 您的查询是 TableAdapter 的方法。 下面的代码替换为 TableAdapter 和查询的名称。 您还需要将任何所需的查询的参数传递。 如果您不确定，如果您的查询需要参数，或它需要哪些参数然后检查查询的所需的签名的 IntelliSense。 具体取决于查询是否带有参数，代码会查找类似于以下示例之一：  
  
     `TableAdapter.Query()`  
  
     `TableAdapter.Query(Parameters)`  
  
     用于声明 TableAdapter 的实例并执行查询的完整代码应类似于下面：  
  
     [!code-csharp[VbRaddataFillingAndExecuting#11](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#11)]
     [!code-vb[VbRaddataFillingAndExecuting#11](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#11)]  
  
## <a name="executing-stored-procedures-that-return-no-value-using-a-command-object"></a>执行存储过程不返回值的使用命令对象  
 下面的示例演示如何创建命令并执行存储的过程不返回值。 有关设置和获取命令的参数值的信息，请参阅[如何： 设置和获取命令对象的参数](http://msdn.microsoft.com/library/10110ecc-d2ed-4796-bb8f-74f2ecd40787)。  
  
 此示例使用<xref:System.Data.SqlClient.SqlCommand>对象，并要求：  
  
-   对引用<xref:System>， <xref:System.Data>，和<xref:System.Xml>命名空间。  
  
#### <a name="to-execute-a-stored-procedure-that-returns-no-value-using-a-datacommand"></a>若要执行存储的过程不返回值使用 DataCommand  
  
-   将以下代码添加到你想要执行存储的过程的方法。 调用`ExecuteNonQuery`方法的某一命令不返回任何值 (例如， <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>)。  
  
     [!code-csharp[VbRaddataFillingAndExecuting#15](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#15)]
     [!code-vb[VbRaddataFillingAndExecuting#15](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#15)]  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 应用程序需要有权访问数据库并执行 SQL 语句。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A?displayProperty=fullName>   
 <xref:System.Data.OleDb.OleDbCommand.ExecuteNonQuery%2A?displayProperty=fullName>   
 <xref:System.Data.Odbc.OdbcCommand.ExecuteNonQuery%2A?displayProperty=fullName>   
 <xref:System.Data.OracleClient.OracleCommand.ExecuteNonQuery%2A?displayProperty=fullName>   
 [如何： 创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)   
 [如何： 编辑 TableAdapter 查询](../data-tools/how-to-edit-tableadapter-queries.md)   
 [如何： 用数据填充数据集](../data-tools/how-to-fill-a-dataset-with-data.md)   
 [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)   
 [如何： 设置和获取命令对象参数](http://msdn.microsoft.com/library/10110ecc-d2ed-4796-bb8f-74f2ecd40787)