---
title: 如何： 安装示例数据库 |Microsoft Docs
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
- sample databases, Adventure Works
- data [Visual Studio], sample databases
- sample databases, Northwind
- Northwind sample database
- Adventure Works sample database
ms.assetid: ed1291f6-604c-4972-ae22-0345c6dea12e
caps.latest.revision: 56
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: fd51bd397e6db3728c10f52db68d45e226fb605b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49251026"
---
# <a name="how-to-install-sample-databases"></a>如何：安装示例数据库
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

许多数据示例都需要能够连接到 Northwind、Pubs 和 AdventureWorks 示例数据库。 你可以按照以下程序安装并连接到这些数据库。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="installing-databases"></a>安装数据库  
 许多数据示例要求能够使用可从网站下载的示例数据库。 示例数据库包括 AdventureWorks、Northwind 和 Pubs 数据库。  
  
#### <a name="to-install-the-northwind-and-pubs-sample-databases-for-sql-server"></a>安装 SQL Server 的 Northwind 和 Pubs 示例数据库  
  
1.  转到[Northwind 和 Pubs 示例数据库](http://go.microsoft.com/fwlink?linkid=64296)web 站点。  
  
2.  下载并运行安装程序。  
  
     安装程序将文件夹添加**SQL Server 2000 Sample Databases**到您的计算机上的根文件夹。 (例如： **C:\SQL Server 2000 Sample Databases**)。  
  
3.  找到你需要的数据库（Northwind 或 Pubs）的 SQL 脚本。  
  
    > [!WARNING]
    >  .MDF 数据库文件无法轻松转换为可在当前 SQL Server 版本中使用的格式，因此最好使用脚本创建数据库。  
  
4.  在中**服务器资源管理器**，创建与你想要安装数据库的 SQL Server 实例的连接。 如果没有特别要用的 SQL Server，可使用随 Visual Studio 自动安装的数据库。 若要执行此操作，指定`(localdb)\v11.0`作为服务器名称。  
  
     若要创建连接，请执行以下步骤。  
  
    ###### <a name="to-create-a-connection-to-an-instance-of-sql-server"></a>创建与 SQL Server 实例的连接  
  
    1.  在中**服务器资源管理器**，打开快捷菜单**数据连接**节点，然后选择**添加连接**。  
  
         **添加连接**对话框随即出现。  
  
    2.  输入要在其中创建 Northwind 或 Pubs 数据库的 SQL Server 的名称，或者输入 (localdb)\v11.0。  
  
    3.  下**选择或输入数据库名称**，从列表中，例如，tempdb 中选择任何数据库。  
  
    4.  选择**测试连接**按钮以验证一切是否正常，，然后选择**确定**按钮。  
  
         新连接节点出现在**服务器资源管理器**。  
  
5.  在您的服务器的连接节点的快捷菜单，然后选择**新查询**按钮。  
  
     编辑器窗口将打开并显示空的 .sql 脚本文件。  
  
6.  将 instnwnd.sql 或 instpubs.sql 的内容粘贴到编辑器窗口。  
  
7.  选择“执行查询”按钮（查询窗口右上方的空心绿色三角图标）。  
  
     如果查询成功，该消息**命令已成功完成**出现。 这意味着 Northwind 或 pubs 数据库创建完成。  
  
     你仍要添加连接到示例数据库。 在中**服务器资源管理器**，打开快捷菜单**数据连接**节点，然后选择**添加连接**。  
  
8.  选择相同数据库服务器之前，但这一次，在选择下选择或输入数据库名称，选择 Northwind 或 pubs 数据库，然后选择**确定**按钮。  
  
     “数据库连接”之下显示示例数据库新节点。  
  
9. 关闭编辑器窗口，确认不保存查询文件。 成功创建数据库之后便不必保存数据库创建脚本。  
  
#### <a name="to-install-the-adventureworks-sample-databases"></a>安装 AdventureWorks 示例数据库  
  
-   下载 AdventureWorks 示例数据库[CodePlex 网站上](http://go.microsoft.com/fwlink/?linkid=87843)。  
  
#### <a name="to-install-the-northwind-sample-database-for-microsoft-access"></a>安装 Microsoft Access 的 Northwind 示例数据库  
  
1.  在 Microsoft Access 2010 或更高版本，northwind，搜索联机模板，然后选择**桌面 Northwind 2007 示例数据库**。  
  
2.  在 Mocrosoft Access 中，将数据库文件保存为 Northwind.accdb。  
  
 Access 数据库的新扩展名是 .accdb。 请参阅[使用 Microsoft Access 2010 进行数据编程](http://msdn.microsoft.com/library/office/ff965871.aspx)。 若要使用访问连接到 Northwind 数据库，请参阅[如何： 连接到 Northwind 数据库](../data-tools/how-to-connect-to-the-northwind-database.md)。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 示例数据库仅用于演示目的，未必展示了最佳安全实践。  
  
## <a name="see-also"></a>请参阅  
 [如何确定 SQL Server 及其组件的版本](http://support.microsoft.com/kb/321185)   
 [使用设计器创建 SQL 数据库](../data-tools/create-a-sql-database-by-using-a-designer.md)   
 [如何：连接到 Northwind 数据库](../data-tools/how-to-connect-to-the-northwind-database.md)