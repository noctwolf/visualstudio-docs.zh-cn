---
title: 连接到 Windows 中的数据窗体应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- System.Data.SqlClient.SqlConnection
- System.Data.Odbc.OdbcConnection
- System.Data.OleDb.OleDbConnection
- System.Data.OracleClient.OracleConnection
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- connection objects, tools for working with
- OleDbConnection class, ADO.NET connection objects
- databases [Visual Studio], connecting to
- data adapters, connections
- connection pooling, ADO.NET connections
- connection strings [Visual Studio], ADO.NET
- connection objects, types of
- dynamic properties, ADO.NET connections
- connections, about connections
- data [Visual Studio], connecting
- design-time connections
- connections, design-time
- TableAdapters, connections
- connection objects
- SqlConnection class, ADO.NET connection objects
- connecting to databases, ADO.NET connections
- transactions, ADO.NET
- database connections [Visual Studio], ADO.NET
ms.assetid: 184cbd0d-3b26-418d-a11c-f9f8f004fbff
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: d8da35b32f3dd25bd7ed47b25f722c6b0aa21ac7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49208944"
---
# <a name="connecting-to-data-in-windows-forms-applications"></a>连接到 Windows 窗体应用程序中的数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 提供了一些工具，用于将应用程序连接到来自许多不同来源（如数据库、Web 服务及对象）的数据。 如果正在使用 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中的数据设计工具，则通常不必为窗体或组件显式创建连接对象。 连接对象通常作为完成一个数据向导或将数据对象拖动到窗体的结果来创建。 若要连接到数据库、 web 服务或对象中的数据应用程序，请运行[数据源配置向导](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)通过选择**添加新数据源**从[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).  
  
 下面的关系图显示通过执行 TableAdapter 查询连接到数据以提取数据并在 Windows 应用程序中的窗体上显示数据时的标准操作流。  
  
 ![客户端应用程序中的数据流](../data-tools/media/clientdatadiagram.gif "ClientDataDiagram")  
  
 在某些情况下，你可能会发现不借助于任何数据设计工具来创建连接对象很方便。 有关以编程方式创建连接的信息，请参阅[连接到数据源](http://msdn.microsoft.com/library/9abc3f92-1be3-4e1a-b360-762dc689650e)。  
  
> [!NOTE]
>  有关 web 应用程序连接到数据的信息，请参阅[ASP.NET 数据访问内容映射](http://msdn.microsoft.com/en-us/f9219396-a0fa-481f-894d-e3d9c67d64f2)。  
  
## <a name="walkthroughs-for-connecting-windows-forms-applications-to-data"></a>将 Windows 窗体应用程序连接到数据的演练  
 以下演练提供了与在 Windows 窗体应用程序中连接到数据相关的过程：  
  
-   [演练： 连接到数据库 （Windows 窗体） 中的数据](http://msdn.microsoft.com/library/02d39aa6-8993-4602-be13-a13536af3d1c)  
  
-   [演练：连接到本地数据库文件中的数据（Windows 窗体）](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md)  
  
-   [演练： 连接到 Web 服务 （Windows 窗体） 中的数据](http://msdn.microsoft.com/library/079fb9b0-c733-40c1-acd1-d0d68834354d)  
  
-   [演练： 连接到对象 （Windows 窗体） 中的数据](http://msdn.microsoft.com/library/21a7fba2-b38b-4726-8cbe-d22154b75a05)  
  
-   [连接到 Access 数据库中的数据（Windows 窗体）](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)  
  
## <a name="creating-connections"></a>创建连接  
 在中[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]，使用配置连接**添加/修改连接**对话框。 **添加连接**编辑或创建一个数据向导中建立的连接时，将显示对话框或[服务器资源管理器/数据库资源管理器](http://msdn.microsoft.com/library/4ea29b3b-bbb2-45e4-9082-eaf635c41c4d)或当正在编辑中的连接属性**属性**窗口。  
  
 执行以下操作之一时将自动配置数据连接。  
  
|操作|描述|  
|------------|-----------------|  
|运行[数据源配置向导](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)。|在选择的数据库路径时，将配置连接**数据源配置向导**。 有关详细信息，请参阅 [How to: Connect to Data in a Database](../data-tools/how-to-connect-to-data-in-a-database.md)。|  
|运行[TableAdapter 配置向导](http://msdn.microsoft.com/library/3a373dd9-7b34-4d3c-a48b-69414512bac8)。|在创建连接**TableAdapter 配置向导**。 有关详细信息，请参阅[创建和配置 Tableadapter](../data-tools/create-and-configure-tableadapters.md)。|  
|运行[编辑 Tableadapter](../data-tools/editing-tableadapters.md)。|在创建连接**TableAdapter 查询配置向导**。 有关详细信息，请参阅[如何： 创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)。|  
|将项从[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)拖动到窗体或[Component Designer](http://msdn.microsoft.com/library/61a3a450-5b15-465e-bd9a-72a6c8c2b282)。|连接对象创建时将项从**数据源**窗口拖到**Windows 窗体设计器**或**组件设计器**。 有关详细信息，请参阅[将控件绑定到 Visual Studio 中的数据](../data-tools/bind-controls-to-data-in-visual-studio.md)。|  
|添加新数据连接到[服务器资源管理器/数据库资源管理器](http://msdn.microsoft.com/library/4ea29b3b-bbb2-45e4-9082-eaf635c41c4d)。|中的数据连接**服务器资源管理器/数据库资源管理器**出现在数据向导中的可用连接列表|  
  
## <a name="connection-strings"></a>连接字符串  
 连接字符串可存储于编译的应用程序或应用程序配置文件中。 有关详细信息，请参阅[如何： 保存和编辑连接字符串](~/E:/Repos/visualstudio-docs-pr/docs/data-tools/how-to-save-and-edit-connection-strings.md)。  
  
## <a name="connection-information-and-security"></a>连接信息和安全性  
 由于打开连接涉及获得对重要资源（数据库）的访问，因此配置和使用连接经常涉及安全性问题。  
  
 如何保护应用程序及其对数据源访问的安全取决于系统的结构。 例如，在基于 Web 的应用程序中，用户通常获得对 Internet 信息服务的匿名访问，因此不提供安全凭据。 在此情况下，应用程序将维护自己的登录信息并使用它（而不是任何特定用户信息）来打开连接和访问数据库。  
  
> [!IMPORTANT]
>  存储连接字符串的详细信息（如密码）可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 集成安全性。 有关详细信息，请参阅[保护连接信息](http://msdn.microsoft.com/library/1471f580-bcd4-4046-bdaf-d2541ecda2f4)。  
  
 在 Intranet 或多层应用程序中，可以利用 Windows、IIS 和 SQL Server 提供的集成安全性选项。 在该模型中，用户在本地网络的身份验证凭据也用于访问数据库资源，并且在连接字符串中不使用任何显式用户名或密码。 通常，通过组在数据库服务器计算机上建立权限，因此你不必为可能访问数据库的每个用户建立单个权限。 在该模型中，你根本不必存储连接的登录信息，并且不需要任何额外步骤来保护连接字符串信息。  
  
 有关安全性的详细信息，请参阅以下主题：  
  
-   [保证 ADO.NET 应用程序的安全](http://msdn.microsoft.com/library/005a1d43-6ee5-471e-ad98-1d30a44d49d5)  
  
-   [在 Windows 窗体中提高文件和数据访问的安全性](http://msdn.microsoft.com/library/3cd3e55b-2f5e-40dd-835d-f50f7ce08967)  
  
## <a name="design-time-connections-in-server-explorerdatabase-explorer"></a>“服务器资源管理器/数据库资源管理器”中的设计时连接  
 **服务器资源管理器/数据库资源管理器**为你创建设计时连接到数据源提供的方法。 它允许你浏览可用的数据源；显示有关它们包含的表、列和其他元素的信息；以及编辑和创建数据库元素。  
  
 你的应用程序不直接使用中的可用连接**服务器资源管理器/数据库资源管理器**。 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 在设计时使用这些连接来处理数据库。 有关详细信息，请参阅[Visual Database Tools](http://msdn.microsoft.com/en-us/6b145922-2f00-47db-befc-bf351b4809a1)。  
  
 例如，在设计时您可能会使用**服务器资源管理器/数据库资源管理器**创建到数据库的连接。 更高版本，在设计窗体时，您可以浏览数据库、 从表中选择列并将它们拖动到[数据集设计器](../data-tools/creating-and-editing-typed-datasets.md)。 这将创建[TableAdapter](../data-tools/tableadapter-overview.md)中你的数据集。 还将创建一个新的连接对象，该对象是新创建的 TableAdapter 的一部分。  
  
 有关设计时连接的信息独立于特定的项目或解决方案存储在本地计算机上。 因此，一旦已建立的设计时连接的应用程序中工作时，它将出现在**服务器资源管理器/数据库资源管理器**每当您从事[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]，只要将服务器连接点不可用。 有关详细信息，请参阅[如何： 从服务器资源管理器连接到数据库](http://msdn.microsoft.com/en-us/7c1c3067-0d77-471b-872b-639f9f50db74)。  
  
 [!INCLUDE[SQLObjectExplorer](../includes/sqlobjectexplorer-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [如何：连接到数据库中的数据](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [演练： 连接到数据库 （Windows 窗体） 中的数据](http://msdn.microsoft.com/library/02d39aa6-8993-4602-be13-a13536af3d1c)   
 [ASP.NET 数据访问内容映射](http://msdn.microsoft.com/en-us/f9219396-a0fa-481f-894d-e3d9c67d64f2)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)