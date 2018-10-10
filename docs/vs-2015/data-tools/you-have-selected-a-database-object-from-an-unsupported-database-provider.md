---
title: 来自不受支持的数据库提供程序选择数据库对象 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8e051a5533f02946e9e28a08abd4c4a1326aca8f
ms.sourcegitcommit: 71218ffc33da325cc1b886f69ff2ca50d44f5f33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "48879291"
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>您从不支持的数据库提供程序选择了数据库对象
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[Visual Studio 2017 文档](/visualstudio/)。  
  
[!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]) 支持的 SQL Server 仅.NET Framework 数据提供程序 (<xref:System.Data.SqlClient>)。 尽管您可以单击**确定**并继续处理来自不受支持的数据库提供程序的对象，您可能会在运行时遇到意外的行为。  
  
> [!NOTE]
>  仅支持使用用于 SQL Server 的 .NET Framework 数据提供程序的数据连接。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   单击**确定**继续设计映射到使用不支持的数据库提供程序的连接的实体类。 使用不支持的数据库提供程序时，可能遇到意外行为。  
  
     或  
  
-   单击**取消**。  
  
     操作停止。 创建或使用采用了用于 SQL Server 的 .NET Framework 提供程序的数据连接。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [.NET framework 数据提供程序](http://msdn.microsoft.com/library/03a9fc62-2d24-491a-9fe6-d6bdb6dcb131)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)

