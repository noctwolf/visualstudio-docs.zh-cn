---
title: 如何： 连接到 Northwind 数据库 |Microsoft Docs
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
- connections [Visual Studio], Northwind database
- Northwind sample database
ms.assetid: cc6cb79f-d035-41f8-b398-8d4a45922bfb
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 2b4393758b4c246af0da830b6ed8d8e20eb8ff40
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49191121"
---
# <a name="how-to-connect-to-the-northwind-database"></a>如何：连接到 Northwind 数据库
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

当你了解如何使用 Visual Studio 创建数据库应用程序时，你将需要连接到 Northwind 数据库，以按照该产品文档中的多个示例进行操作。 根据你要遵循的示例，你将连接到  SQL Server 或数据库文件中的数据库，例如，适用于 Microsoft Access 或 SQL Server 的一个数据库。  
  
## <a name="creating-data-connections-to-the-northwind-database"></a>创建到 Northwind 数据库的数据连接  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-create-a-data-connection-to-the-northwind-database-sql-server"></a>创建到 Northwind 数据库（SQL Server）的数据连接  
  
1.  上**视图**菜单中，选择**服务器资源管理器**/**数据库资源管理器**。  
  
2.  在中**服务器资源管理器**/**数据库资源管理器**，打开快捷菜单**数据连接**，然后选择**添加连接**.  
  
     选择后**添加连接**、 任一**选择数据源**对话框或**添加连接**对话框将出现。  
  
3.  如果**选择数据源**对话框后，选择**Microsoft SQL Server**，然后选择**确定**。  
  
     如果**添加连接**对话框随即出现并**数据源**不是**Microsoft SQL Server (SqlClient)**，选择**更改**按钮以打开**更改数据源**对话框中，选择**Microsoft SQL Server**，然后选择**确定**按钮。  
  
4.  在中**服务器名称**列表中，指定 Northwind 数据库所在的服务器的名称。  
  
5.  根据你的 SQL Server 和 Northwind 数据库版本的要求，选择**使用 Windows 身份验证**或选择**使用 SQL Server 身份验证**并输入用户名和若要登录到运行 SQL Server 的计算机上的密码。  
  
6.  选择 Northwind 数据库中的**选择或输入数据库名称**列表。  
  
7.  选择**测试连接**来验证到 Northwind 数据库的连接。  
  
8.  选择 **“确定”**。  
  
     到 Northwind 数据库的数据连接添加到**服务器资源管理器**/**数据库资源管理器**。  
  
 除了连接到 SQL Server 数据库的远程实例外，你还可以直接连接到包含该数据库的实际文件。 这样，你就可以将数据库文件直接添加到项目中，在该项目中可将这些文件部署为应用程序的一部分。 目前支持以下本地数据库文件： SQL Server Compact 数据库文件 (.sdf)[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]和 SQL Server Express 数据库文件 (.mdf) 和 Microsoft Access 数据库文件 （.mdb 或.accdb）。  
  
#### <a name="to-create-a-data-connection-to-the-northwind-databasesql-server-database-file-mdf"></a>创建到 Northwind 数据库的数据连接 – SQL Server 数据库文件 (.mdf)  
  
1.  上**视图**菜单中，选择**服务器资源管理器**/**数据库资源管理器**。  
  
2.  在中**服务器资源管理器**/**数据库资源管理器**，打开快捷菜单**数据连接**，然后选择**添加连接**.  
  
     选择后**添加连接**、 任一**添加连接**对话框或**选择数据源**对话框将出现。  
  
3.  如果**选择数据源**对话框后，选择**Microsoft SQL Server 数据库文件**，然后选择**确定**。  
  
4.  如果**添加连接**出现对话框，请确认**数据源**设置为**Microsoft SQL Server 数据库文件 (SqlClient)**。 如果未设置为**Microsoft SQL Server 数据库文件 (SqlClient)**，选择**更改**以打开**更改数据源**对话框框中，选择**Microsoft SQL服务器数据库文件**，然后选择**确定**按钮。  
  
5.  选择**浏览**以查找包含 Northwind 数据库的.mdf 文件。  
  
6.  根据你的 Northwind 数据库版本的要求，选择**使用 Windows 身份验证**或选择**SQL Server 身份验证**并输入用户名和密码登录到运行 SQL Server 的计算机。  
  
7.  选择“确定”  按钮。  
  
     到 Northwind 数据库的数据连接添加到**服务器资源管理器**/**数据库资源管理器**。  
  
> [!NOTE]
>  [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] 具有应用到 Northwind 数据库文件 (.mdf) 的更改。 有关信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
#### <a name="to-create-a-data-connection-to-the-northwind-databaseaccess-database-file-mdb-or-accdb"></a>创建与 Northwind 数据库的数据连接 — Access 数据库文件 (.mdb 或 .accdb)  
  
1.  上**视图**菜单中，选择**服务器资源管理器**/**数据库资源管理器**。  
  
2.  在中**服务器资源管理器**/**数据库资源管理器**，打开快捷菜单**数据连接**，然后选择**添加连接**.  
  
     选择后**添加连接**、 任一**添加连接**对话框或**选择数据源**对话框将出现。  
  
3.  如果**选择数据源**对话框后，选择**Microsoft Access 数据库文件**，然后选择**确定**。  
  
4.  如果**添加连接**出现对话框，请确认**数据源**设置为**Microsoft Access 数据库文件**。 如果未设置为**Microsoft Access 数据库文件**，选择**更改**以打开**更改数据源**对话框框中，选择**Microsoft Access 数据库文件**，然后选择**确定**按钮。  
  
5.  选择**浏览**以查找包含 Northwind 数据库的.mdb 或.accdb 文件。  
  
6.  如果你的 Northwind 数据库版本要求用户名和密码，请输入用户名和密码。  
  
7.  选择 **“确定”**。  
  
     到 Northwind 数据库的数据连接添加到**服务器资源管理器**/**数据库资源管理器**。  
  
## <a name="see-also"></a>请参阅  
 [如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)   
 [使用 Microsoft Access 2010 进行数据编程](http://msdn.microsoft.com/library/office/ff965871.aspx)   
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)