---
title: 演练： 为 Northwind Customers 表创建更新存储过程 |Microsoft Docs
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
- Northwind sample database
- stored procedures [Visual Studio]
- O/R Designer, stored procedures
ms.assetid: 6fd9e7e0-6862-44d3-9710-acc5a72d4ffd
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: bbcd68b7604f7a80546168406146f326e1bac224
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468919"
---
# <a name="walkthrough-creating-update-stored-procedures-for-the-northwind-customers-table"></a>演练：为 Northwind Customers 表创建更新存储过程
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

中的一些帮助主题[!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)]文档需要 Northwind 示例数据库中的其他存储的过程在客户表中执行更新 （插入、 更新和删除） 的数据。  
  
 本演练为 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 提供了用于在 Northwind 示例数据库中创建这些附加存储过程的指令。  
  
 本主题后面的“后续步骤”一节提供了一些链接，指向演示如何使用这些附加存储过程的主题。  
  
 在本演练中，你将学习如何执行以下任务：  
  
-   创建到 Northwind 示例数据库的数据连接。  
  
-   创建存储过程。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你需要：  
  
-   访问 Northwind 示例数据库的 SQL Server 版本。 有关详细信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
## <a name="connecting-to-the-northwind-database"></a>连接到 Northwind 数据库  
 本演练要求连接到 Northwind 数据库的 SQL Server 版本。 以下过程提供了用于创建数据连接的指令。  
  
> [!NOTE]
>  如果你已经具有到 Northwind 数据库的数据连接，则可以进入下一节：创建存储过程。  
  
#### <a name="to-create-a-data-connection-to-the-northwind-sql-server-database"></a>创建到 Northwind SQL Server 数据库的数据连接  
  
1.  上**视图**菜单上，单击**服务器资源管理器**/**数据库资源管理器**。  
  
2.  右键单击**数据连接**然后单击**添加连接**。  
  
3.  在中**选择数据源**对话框中，单击**Microsoft SQL Server**，然后单击**确定**。  
  
     如果**添加连接**对话框将打开，并**数据源**不是**Microsoft SQL Server (SqlClient)**，单击**更改**打开**选择/更改数据源**对话框中，单击**Microsoft SQL Server**，然后单击**确定**。  
  
4.  单击**服务器名称**下拉列表中列出，或键入 Northwind 数据库所在的服务器的名称。  
  
5.  根据数据库或应用程序的要求，或者单击**使用 Windows 身份验证**或使用特定用户名和密码登录到运行 SQL Server 的计算机上 (**SQL Server 身份验证**).  
  
6.  单击 Northwind 数据库中的**选择或输入数据库名称**列表。  
  
7.  单击 **“确定”**。  
  
     数据连接添加到**服务器资源管理器**/**数据库资源管理器**。  
  
## <a name="creating-the-stored-procedures"></a>创建存储过程  
 通过使用对 Northwind 数据库运行提供的 SQL 脚本创建的存储的过程[Visual Database Tools](http://msdn.microsoft.com/en-us/6b145922-2f00-47db-befc-bf351b4809a1)推出**服务器资源管理器**/ **数据库资源管理器**。  
  
#### <a name="to-create-the-stored-procedures-by-using-a-sql-script"></a>使用 SQL 脚本创建存储过程  
  
1.  展开 Northwind 数据库中的**服务器资源管理器**/**数据库资源管理器**。  
  
2.  右键单击**存储过程**节点，然后单击**添加新存储过程**。  
  
3.  将以下代码粘贴到“代码编辑器”中，从而替换 `CREATE PROCEDURE` 模板：  
  
    ```  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'SelectCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.[SelectCustomers]  
    GO  
  
    CREATE PROCEDURE dbo.[SelectCustomers]  
    AS  
        SET NOCOUNT ON;  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM dbo.Customers  
    GO  
  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'InsertCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.InsertCustomers  
    GO  
  
    CREATE PROCEDURE dbo.InsertCustomers  
    (  
        @CustomerID nchar(5),  
        @CompanyName nvarchar(40),  
        @ContactName nvarchar(30),  
        @ContactTitle nvarchar(30),  
        @Address nvarchar(60),  
        @City nvarchar(15),  
        @Region nvarchar(15),  
        @PostalCode nvarchar(10),  
        @Country nvarchar(15),  
        @Phone nvarchar(24),  
        @Fax nvarchar(24)  
    )  
    AS  
        SET NOCOUNT OFF;  
    INSERT INTO [dbo].[Customers] ([CustomerID], [CompanyName], [ContactName], [ContactTitle], [Address], [City], [Region], [PostalCode], [Country], [Phone], [Fax]) VALUES (@CustomerID, @CompanyName, @ContactName, @ContactTitle, @Address, @City, @Region, @PostalCode, @Country, @Phone, @Fax);  
  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM Customers WHERE (CustomerID = @CustomerID)  
    GO  
  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'UpdateCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.UpdateCustomers  
    GO  
  
    CREATE PROCEDURE dbo.UpdateCustomers  
    (  
        @CustomerID nchar(5),  
        @CompanyName nvarchar(40),  
        @ContactName nvarchar(30),  
        @ContactTitle nvarchar(30),  
        @Address nvarchar(60),  
        @City nvarchar(15),  
        @Region nvarchar(15),  
        @PostalCode nvarchar(10),  
        @Country nvarchar(15),  
        @Phone nvarchar(24),  
        @Fax nvarchar(24),  
        @Original_CustomerID nchar(5)  
    )  
    AS  
        SET NOCOUNT OFF;  
    UPDATE [dbo].[Customers] SET [CustomerID] = @CustomerID, [CompanyName] = @CompanyName, [ContactName] = @ContactName, [ContactTitle] = @ContactTitle, [Address] = @Address, [City] = @City, [Region] = @Region, [PostalCode] = @PostalCode, [Country] = @Country, [Phone] = @Phone, [Fax] = @Fax WHERE (([CustomerID] = @Original_CustomerID));  
  
    SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax FROM Customers WHERE (CustomerID = @CustomerID)  
    GO  
  
    IF EXISTS (SELECT * FROM sysobjects WHERE name = 'DeleteCustomers' AND user_name(uid) = 'dbo')  
        DROP PROCEDURE dbo.DeleteCustomers  
    GO  
  
    CREATE PROCEDURE dbo.DeleteCustomers  
    (  
        @Original_CustomerID nchar(5)  
    )  
    AS  
        SET NOCOUNT OFF;  
    DELETE FROM [dbo].[Customers] WHERE (([CustomerID] = @Original_CustomerID))  
    GO  
    ```  
  
4.  在代码编辑器中选择所有文本，右键单击所选的文本，然后单击**运行选定内容**。  
  
     将为 Northwind 数据库创建 electCustomers、InsertCustomers、UpdateCustomers 和 eleteCustomers 存储过程。  
  
## <a name="next-steps"></a>后续步骤  
 现在你已经创建了存储过程，请尝试以下演示如何使用它们的演练：  
  
 [如何：分配存储过程以便执行更新、插入和删除操作（O/R 设计器）](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)  
  
 [演练： 创建 LINQ to SQL 类 （O-R 设计器）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)  
  
 [演练：自定义实体类的插入、更新和删除行为](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [在 Visual Studio 中访问数据](../data-tools/accessing-data-in-visual-studio.md)