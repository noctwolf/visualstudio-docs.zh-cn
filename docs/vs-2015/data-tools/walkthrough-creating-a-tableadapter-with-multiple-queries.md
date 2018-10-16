---
title: 演练： 创建带有多个查询的 TableAdapter |Microsoft Docs
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
- TableAdapter queries, creating
- data [Visual Studio], TableAdapters
- TableAdapters, creating
- data [Visual Studio], walkthroughs
- queries [Visual Studio], TableAdapters
ms.assetid: f784dc4d-d514-4ade-8226-f8271c5b1ed8
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 4226fc805ed0335109d0a6b98f1235ae46de1664
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49206695"
---
# <a name="walkthrough-creating-a-tableadapter-with-multiple-queries"></a>演练：创建带有多个查询的 TableAdapter
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在本演练中，你将创建数据集使用 TableAdapter[数据源配置向导](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)。 本演练将指导你完成创建第二个查询中的过程[TableAdapter](../data-tools/tableadapter-overview.md)使用[编辑 Tableadapter](../data-tools/editing-tableadapters.md)内[数据集设计器](../data-tools/creating-and-editing-typed-datasets.md)。  
  
 本演练涉及以下任务：  
  
-   创建一个新**Windows 应用程序**项目。  
  
-   创建和配置应用程序中的数据源，通过生成具有的数据集**数据源配置向导**。  
  
-   打开中的新数据集**数据集设计器**。  
  
-   将查询添加到与 TableAdapter **TableAdapter 查询配置向导**。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你需要：  
  
-   访问 Northwind 示例数据库（SQL Server 或 Access 版）。 有关详细信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
## <a name="creating-a-new-windows-application"></a>创建新的 Windows 应用程序  
 第一步是创建 Windows 应用程序。  
  
#### <a name="to-create-a-new-windows-application-project"></a>创建新的 Windows 应用程序项目  
  
1.  在中[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]，从**文件**菜单中，创建一个新项目。  
  
2.  选择一种编程语言中的**项目类型**窗格。  
  
3.  单击**Windows 应用程序**中**模板**窗格。  
  
4.  将项目命名`TableAdapterQueriesWalkthrough`，然后单击**确定**。  
  
     Visual Studio 将添加到项目**解决方案资源管理器**，并在设计器中显示新窗体。  
  
## <a name="creating-a-database-data-source-with-a-tableadapter"></a>使用 TableAdapter 创建数据库数据源  
 此步骤中创建一个数据源使用**数据源配置向导**基于`Customers`Northwind 示例数据库中的表。 你必须具有对 Northwind 示例数据库的访问权限，才能创建连接。 有关设置 Northwind 示例数据库的信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
#### <a name="to-create-the-data-source"></a>创建数据源  
  
1.  在 **“数据”** 菜单上，单击 **“显示数据源”**。  
  
2.  在中**数据源**窗口中，选择**添加新数据源**以启动**数据源配置向导**。  
  
3.  在 **“选择数据源类型”** 页上选择 **“数据库”** ，然后单击 **“下一步”**。  
  
4.  上**选择您的数据连接**页面上执行以下项之一：  
  
    -   如果下拉列表中包含到 Northwind 示例数据库的数据连接，请选择该连接。  
  
         或  
  
    -   选择**新的连接**以启动**添加/修改连接**对话框。  
  
5.  如果你的数据库需要密码，选择选项以包括敏感数据，然后单击**下一步**。  
  
6.  单击**下一步**上**将连接字符串保存到应用程序配置文件**页。  
  
7.  展开**表**上的节点**选择数据库对象**页。  
  
8.  选择**客户**表，并单击**完成**。  
  
     **NorthwindDataSet**添加到项目并**客户**表中将显示**数据源**窗口。  
  
## <a name="opening-the-dataset-in-the-dataset-designer"></a>在数据集设计器中打开数据集  
  
#### <a name="to-open-the-dataset-in-the-dataset-designer"></a>在“数据集设计器”中打开数据集  
  
1.  右键单击**NorthwindDataset**中**数据源**窗口。  
  
2.  在快捷菜单上，选择**与设计器编辑数据集**。  
  
     在中打开 NorthwindDataset**数据集设计器**。  
  
## <a name="adding-a-second-query-to-the-customerstableadapter"></a>向 CustomersTableAdapter 中添加第二个查询  
 该向导创建的数据集**客户**数据表并**CustomersTableAdapter**。 本演练的本部分将添加到第二个查询**CustomersTableAdapter**。  
  
#### <a name="to-add-a-query-to-the-customerstableadapter"></a>将查询添加到 CustomersTableAdapter 中  
  
1.  拖动**查询**从**数据集**选项卡**工具箱**拖到**客户**表。  
  
     [编辑 Tableadapter](../data-tools/editing-tableadapters.md)随即打开。  
  
2.  选择**使用 SQL 语句**，然后单击**下一步**。  
  
3.  选择**选择返回的行**，然后单击**下一步**。  
  
4.  将 WHERE 子句添加到查询，结果为：  
  
    ```  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax   
    FROM Customers   
    WHERE City = @City  
    ```  
  
    > [!NOTE]
    >  如果使用的 Access 版的 Northwind，将为@City参数用问号。 (`SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM Customers WHERE City = ?`)  
  
5.  上**生成的选择方法**页上，命名**填充 DataTable**方法`FillByCity`。  
  
    > [!NOTE]
    >  此方法能够**返回 DataTable**不用于本演练中，因此您可以清除该复选框或保留默认名称。  
  
6.  单击**下一步**，然后完成向导。  
  
     **FillByCity**查询添加到**CustomersTableAdapter**。  
  
## <a name="adding-code-to-execute-the-additional-query-on-the-form"></a>在窗体上添加执行其他查询的代码  
  
#### <a name="to-execute-the-query"></a>执行查询  
  
1.  选择**Form1**中**解决方案资源管理器**，然后单击**视图设计器**。  
  
2.  拖动**客户**从节点**数据源**窗口**Form1**。  
  
3.  通过选择更改到代码视图**代码**从**视图**菜单。  
  
4.  将 `Form1_Load` 事件处理程序中的代码替换为以下运行 `FillByCity` 查询的代码。  
  
     [!code-csharp[VbRaddataTableAdapters#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataTableAdapters/CS/Form1.cs#1)]
     [!code-vb[VbRaddataTableAdapters#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataTableAdapters/VB/Form1.vb#1)]  
  
## <a name="running-the-application"></a>运行应用程序  
  
#### <a name="to-run-the-application"></a>运行应用程序  
  
-   按 F5。  
  
-   网格将由 `City` 值为 `Seattle` 的客户进行填充。  
  
## <a name="next-steps"></a>后续步骤  
  
### <a name="to-add-functionality-to-your-application"></a>将功能添加到你的应用程序  
  
-   添加一个 <xref:System.Windows.Forms.TextBox> 控件和 <xref:System.Windows.Forms.Button> 控件，并将文本框中的值传递给查询。 (`CustomersTableAdapter.FillByCity(NorthwindDataSet.Customers, TextBox1.Text)`).  
  
-   将验证逻辑添加到该数据集中数据表的 <xref:System.Data.DataTable.ColumnChanging> 或 <xref:System.Data.DataTable.RowChanging> 事件中。 有关详细信息，请参阅[验证数据集中](../data-tools/validate-data-in-datasets.md)。  
  
## <a name="see-also"></a>请参阅  
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)   
 [创建和配置 Tableadapter](../data-tools/create-and-configure-tableadapters.md)   
 [如何： 创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)   
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [在应用程序中编辑数据](../data-tools/editing-data-in-your-application.md)