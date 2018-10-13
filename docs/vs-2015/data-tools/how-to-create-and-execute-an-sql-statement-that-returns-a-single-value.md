---
title: 如何： 创建和执行返回单个值的 SQL 语句 |Microsoft Docs
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
- data reader
- scalar values
- stored procedures, returning single value
- SQL statements, data commands
- DataReader object
- data commands, returning scalar values
ms.assetid: eb366496-69e5-4462-8683-653054165c5c
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 7d5d57637a25db62832ad535bbad60214a0aa4ad
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49192148"
---
# <a name="how-to-create-and-execute-an-sql-statement-that-returns-a-single-value"></a>如何：创建和执行返回单个值的 SQL 语句
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

若要执行返回单个值的 SQL 语句，可以运行 TableAdapter 查询配置为运行 SQL 语句 (例如， `CustomersTableAdapter.CustomerCount()`)。  
  
 如果你的应用程序不使用 Tableadapter，调用`ExecuteScalar`上设置的命令对象的方法及其`CommandType`属性设置为<xref:System.Data.CommandType>。 ("命令对象"指与特定的命令[.NET Framework 数据提供程序](http://msdn.microsoft.com/library/03a9fc62-2d24-491a-9fe6-d6bdb6dcb131)使用你的应用程序。 例如，如果你的应用程序使用适用于 SQL Server 的.NET Framework 数据提供程序，命令对象都是<xref:System.Data.SqlClient.SqlCommand>。)  
  
 以下示例演示如何执行返回单个值，使用任一 Tableadapter 从数据库的 SQL 语句或命令对象。 使用 Tableadapter 和命令进行查询的详细信息，请参阅[使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="executing-sql-statements-that-return-single-values-using-a-tableadapter"></a>执行返回单个值使用 TableAdapter 的 SQL 语句  
 此示例演示如何创建 TableAdapter 查询使用[编辑 Tableadapter](../data-tools/editing-tableadapters.md)，然后它提供有关如何声明 TableAdapter 的实例和执行查询信息。  
  
#### <a name="to-create-an-sql-statement-returning-a-single-value-using-a-tableadapter"></a>若要创建 SQL 语句返回一个值，使用 TableAdapter  
  
1.  打开中的数据集**数据集设计器**。 有关详细信息，请参阅[如何： 在数据集设计器中打开数据集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
2.  如果你还没有一个创建的 TableAdapter。 创建 Tableadapter 的详细信息，请参阅[创建和配置 Tableadapter](../data-tools/create-and-configure-tableadapters.md)。  
  
3.  如果你使用的 SQL 语句以返回单个值的 TableAdapter 上已有一个查询，然后跳到下一个过程，""声明的 TableAdapter 实例并执行查询。 否则，继续执行步骤 4，以创建新的查询返回单个值。  
  
4.  右键单击你想，TableAdapter 并使用快捷菜单添加查询。  
  
     **TableAdapter 查询配置向导**随即打开。  
  
5.  保留默认值为**使用 SQL 语句**，然后单击**下一步**。  
  
6.  选择**选择返回单个值**选项，并单击**下一步**。  
  
7.  键入 SQL 语句，或使用**查询生成器**以创建一条，然后单击**下一步**。  
  
8.  提供查询的名称。  
  
9. 完成向导。将查询添加到 TableAdapter。  
  
10. 生成你的项目。  
  
#### <a name="to-declare-an-instance-of-the-tableadapter-and-execute-the-query"></a>若要声明的 TableAdapter 实例并执行查询  
  
1.  声明包含你想要执行的查询的 TableAdapter 的实例。  
  
    -   若要创建使用设计时工具的实例，将想要从 TableAdapter**工具箱**。 (现在在项目中的组件中将出现**工具箱**标题下的项目名称相匹配。)如果未出现在 TableAdapter**工具箱**，则需要生成项目。  
  
         或  
  
    -   若要在代码中创建一个实例，将的名称替换为以下代码在<xref:System.Data.DataSet>和 TableAdapter。  
  
         `Dim tableAdapter As New DataSetTableAdapters.TableAdapter`  
  
        > [!NOTE]
        >  不在其关联的数据集类中使用实际位于 Tableadapter。 每个数据集具有自己的命名空间中的相应集合的 Tableadapter。 例如，如果您有一个名为的数据集`SalesDataSet`，则不会有`SalesDataSetTableAdapters`包含其 Tableadapter 的命名空间。  
  
2.  在代码中调用任何其他方法的方式，请调用您的查询。 您的查询是 TableAdapter 的方法。 下面的代码替换为 TableAdapter 和查询的名称。 此外需要传入所需查询的任何参数，并使用返回的值执行某些操作 （例如，将其分配给一个变量）。 如果您不确定，如果您的查询需要参数，或它需要哪些参数然后检查查询的所需的签名的 IntelliSense。 具体取决于查询是否带有参数，代码会查找类似于以下示例之一：  
  
     `TableAdapter.Query()`  
  
     `TableAdapter.Query(Parameters)`  
  
3.  您可能需要将分配给的变量由查询返回的值。 返回单个值的 TableAdapter 查询会返回基于查询的数据类型 (而不是`ExecuteScalar`方法，返回的对象)。 例如，如果 TableAdapter 查询选择单个列的数据类型是一个整数，该查询的返回值是整数。 如果列允许 null 值，返回值是可以为 null 的类型之一 (例如， `Nullable(Of Integer)`)。 可以为 null 的类型的详细信息，请参阅<xref:System.Nullable>。 用于声明 TableAdapter 的实例并执行查询的完整代码应如下所示 (此示例假定返回值是一个整数; 请调整你的代码根据查询返回的数据类型):  
  
     [!code-csharp[VbRaddataFillingAndExecuting#9](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#9)]
     [!code-vb[VbRaddataFillingAndExecuting#9](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#9)]  
  
## <a name="executing-sql-statements-that-return-single-values-using-a-command-object"></a>执行返回单个值使用命令对象的 SQL 语句  
 下面的示例演示如何创建命令和执行返回单个值的 SQL 语句。 有关设置和获取命令的参数值的信息，请参阅[如何： 设置和获取命令对象的参数](http://msdn.microsoft.com/library/10110ecc-d2ed-4796-bb8f-74f2ecd40787)。  
  
 此示例使用<xref:System.Data.SqlClient.SqlCommand>对象，并要求：  
  
-   对引用<xref:System>， <xref:System.Data>，和<xref:System.Xml>命名空间。  
  
-   名为的数据连接`SqlConnection1`。  
  
-   名为的表`Customers`的数据源中的`SqlConnection1`相连。 （否则，您需要有效的 SQL 语句为您的数据源）。  
  
#### <a name="to-execute-an-sql-statement-returning-a-single-value-using-a-datacommand"></a>若要执行返回单个值使用 DataCommand 的 SQL 语句  
  
-   将以下代码添加到你想要执行的代码的方法。 通过调用返回单个值`ExecuteScalar`命令的方法 (例如， <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>)。 返回的数据<xref:System.Object>。  
  
     [!code-csharp[VbRaddataFillingAndExecuting#10](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form2.cs#10)]
     [!code-vb[VbRaddataFillingAndExecuting#10](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form2.vb#10)]  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 应用程序需要有权访问数据库并执行 SQL 语句。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A?displayProperty=fullName>   
 <xref:System.Data.OleDb.OleDbCommand.ExecuteScalar%2A?displayProperty=fullName>   
 <xref:System.Data.Odbc.OdbcCommand.ExecuteScalar%2A?displayProperty=fullName>   
 <xref:System.Data.OracleClient.OracleCommand.ExecuteScalar%2A?displayProperty=fullName>   
 [如何： 创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)   
 [如何： 编辑 TableAdapter 查询](../data-tools/how-to-edit-tableadapter-queries.md)   
 [如何： 用数据填充数据集](../data-tools/how-to-fill-a-dataset-with-data.md)   
 [使用 Tableadapter 填充数据集](../data-tools/fill-datasets-by-using-tableadapters.md)   
 [如何： 设置和获取命令对象参数](http://msdn.microsoft.com/library/10110ecc-d2ed-4796-bb8f-74f2ecd40787)