---
title: 如何： 将数据集更改保存到数据库 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DbDataAdapter.Update
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], saving
- databases, updating
- updating datasets, writing changes to data source
ms.assetid: c9970150-b71b-4c9d-a355-5efb6b510dca
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: a197952bcc392f84db3f612a158817237e077d36
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49202275"
---
# <a name="how-to-save-dataset-changes-to-a-database"></a>如何：将数据集更改保存到数据库中
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在数据集中的数据已修改并验证后，你可能想要将更新后的数据发送回数据库。 若要将修改后的数据发送到数据库，您调用`Update`方法[TableAdapter](../data-tools/tableadapter-overview.md)或数据适配器。 该适配器`Update`方法更新单个数据表，并执行正确的命令 （INSERT、 UPDATE 或 DELETE） 基于<xref:System.Data.DataRow.RowState%2A>的表中每个数据行。  
  
 将数据保存在相关表中，Visual Studio 提供了可帮助您进行基于数据库中定义的外键约束的正确顺序执行保存一个 TableAdapterManager 组件。 有关详细信息，请参阅[分层更新概述](http://msdn.microsoft.com/library/c4f8e8b9-e4a5-4a02-8462-d03d1e8222d6)。  
  
> [!NOTE]
>  尝试更新数据源的数据集内容会导致错误，因为将应调用该适配器的代码放`Update`方法的内部`try` / `catch`块。  
  
 更新数据源确切过程可能会有所不同，具体取决于你的业务需求，但你的应用程序应包括以下步骤：  
  
1.  执行代码时，尝试将更新发送到该数据库在`try` / `catch`块。  
  
2.  如果捕获到异常，找到导致此错误的数据行。 有关详细信息，请参阅[如何： 查找具有错误的行](http://msdn.microsoft.com/library/1fa907c5-fe66-4f29-a253-2b97b900050c)。  
  
3.  解决此问题在数据行 （如果可能，则以编程方式或无效的行显示给用户进行修改），然后再重新尝试更新 (<xref:System.Data.DataRow.HasErrors%2A>属性，<xref:System.Data.DataTable.GetErrors%2A>方法)。  
  
## <a name="saving-data-to-a-database"></a>将数据保存到数据库  
 调用`Update`TableAdapter 或数据适配器，将数据表的名称传递方法，包含要写入到数据库的值。 将数据从单个数据表保存回数据库的详细信息，请参阅[演练： 将数据保存到数据库 （单个表）](http://msdn.microsoft.com/library/68befa96-7463-43e8-abcf-dc2f42ccd53d)。  
  
#### <a name="to-update-a-database-with-a-dataset-using-a-tableadapter"></a>若要使用的数据集使用 TableAdapter 更新数据库  
  
-   将括`TableAdapter.Update`方法内的`try` / `catch`块。 下面的示例演示如何尝试将更新的内容与`Customers`表中`NorthwindDataSet`。  
  
     [!code-csharp[VbRaddataSaving#9](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#9)]
     [!code-vb[VbRaddataSaving#9](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#9)]  
  
#### <a name="to-update-a-database-with-a-dataset-using-a-data-adapter"></a>若要使用数据适配器为数据集使用更新数据库  
  
-   将括`DataAdapter.Update`方法内的`try` / `catch`块。 下面的示例演示如何尝试对数据源的内容的更新`Table1`在`DataSet1`。  
  
     [!code-csharp[VbRaddataSaving#26](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#26)]
     [!code-vb[VbRaddataSaving#26](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#26)]  
  
## <a name="updating-two-related-tables-in-a-dataset"></a>更新数据集中的两个相关的表  
 当更新在数据集中的相关的表时，务必更新以正确的顺序，降低违反引用完整性约束的可能性。 命令执行的顺序也将遵循的索引<xref:System.Data.DataRowCollection>在数据集中。 若要防止数据完整性错误而引发，最佳做法是以更新数据库，按以下顺序：  
  
1.  子表： 删除记录。  
  
2.  父表： 插入、 更新和删除记录。  
  
3.  子表： 插入和更新记录。  
  
 将数据保存从多个表的详细信息，请参阅[将数据保存到数据库 （多个表）](../data-tools/save-data-to-a-database-multiple-tables.md)。  
  
 如果要更新两个或多个相关的表，则应包含在一个事务内的所有更新逻辑。 事务是指一个过程，它首先确保对数据库的所有相关更改均可成功完成，然后再提交更改。 有关详细信息，请参阅[事务和并发性](http://msdn.microsoft.com/library/f46570de-9e50-4fe6-8710-a8c31fa8569b)。  
  
#### <a name="to-update-two-related-tables-using-a-tableadapter"></a>若要更新使用 TableAdapter 的两个相关的表  
  
1.  创建三个临时<xref:System.Data.DataTable>s 来保存不同的记录。  
  
2.  调用`Update`方法中的行的每个子集`try` / `catch`块。 如果出现更新错误，建议过程是操作的分支出来并解决这些问题。  
  
3.  从数据集所做的更改提交到数据库中。  
  
4.  释放临时数据的表以释放资源。  
  
     [!code-csharp[VbRaddataSaving#27](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form2.cs#27)]
     [!code-vb[VbRaddataSaving#27](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form2.vb#27)]  
  
#### <a name="to-update-two-related-tables-using-a-data-adapter"></a>若要更新使用数据适配器的两个相关的表  
  
-   调用`Update`的每个数据适配器的方法。  
  
     下面的示例演示如何使用包含相关的表的数据集更新数据源。 若要理解上述过程中，三个临时<xref:System.Data.DataTable>将创建 s 来保存不同的记录。 然后`Update`方法将从内部调用的每个行的子集`try` / `catch`块。 如果出现更新错误，建议过程是操作的分支出来并解决这些问题。 然后，数据集提交所做的更改。 最后，释放临时数据的表以释放资源。  
  
     [!code-csharp[VbRaddataSaving#28](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#28)]
     [!code-vb[VbRaddataSaving#28](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>请参阅  
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)