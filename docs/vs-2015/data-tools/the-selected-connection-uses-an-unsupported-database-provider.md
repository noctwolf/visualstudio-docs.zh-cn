---
title: 所选的连接使用不支持的数据库提供程序 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e4e717bf0f1da2b7b25d62d4639690ae1cce0273
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49241353"
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>所选连接使用不支持的数据库提供程序
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
当拖动项适用于 SQL Server 不使用.NET Framework 数据提供程序时，会出现此消息**服务器资源管理器**/**数据库资源管理器**拖到[LINQ to SQL在 Visual Studio 中的工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)。  
  
 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]仅支持使用用于 SQL Server 的 .NET Framework 提供程序的数据连接。 只有指向 Microsoft SQL Server 或 Microsoft SQL Server 数据库文件的连接才有效。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   仅当项来自于使用用于 SQL Server 的 .NET Framework 数据提供程序的数据连接时，才将其添加到 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]中。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.SqlClient>   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [.NET framework 数据提供程序](http://msdn.microsoft.com/library/03a9fc62-2d24-491a-9fe6-d6bdb6dcb131)   
 [演练： 创建 LINQ to SQL 类 （O-R 设计器）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [创建数据应用程序](../data-tools/creating-data-applications.md)

