---
title: 本地数据概述 |Microsoft Docs
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
- SQL Server Express
- local data
- SQL Server LocalDB
- LocalDB
- SQLEXPRESS
- SQL Server, local data
- SQL Express
- SQL Server Compact
- data access [Visual Studio], troubleshooting
- Access, .mdb files in Visual Studio
- data [Visual Studio], local
ms.assetid: d6afa5ac-2bb8-49f2-a50e-f71f611ed506
caps.latest.revision: 71
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 94b3f066a66a380875609b4f6485d56a19ebde3e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49885572"
---
# <a name="local-data-overview"></a>本地数据概述
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

开发数据应用程序，它时，通常最好使用数据库的本地副本，以便不到生产数据引入错误。 如果两个开发人员引发错误，难检测方式进行交互，甚至与其他开发人员共享测试数据库创建潜在问题。 可以通过在本地计算机上使用你自己的测试数据来避免这些缺陷。 如果不是所有数据库系统的大多数使你可以创建本地数据文件。 对于.NET 项目，Visual Studio 供本地 SQL Server 数据库文件 (.mdf) 和 Microsoft Access 数据库文件 (.mdb) 提供特殊支持。  
  
 Visual Studio 支持这些方案：  
  
1.  
  
2.  
  
- 
  
- 
  
- 通过单击解决方案资源管理器中的解决方案节点，然后选择创建一个 SQL Server 数据库项目**添加&#124;新建项目**。  在左窗格中，选择**SQL Server&#124;数据库**项目，然后单击确定。 在解决方案资源管理器，右键单击数据库项目节点，以导入本地数据库文件，然后开发连接到数据库项目生成的应用程序。 在开发和您在开发应用程序的同时修改数据库架构时适用。  
  
   ![数据库导入数据库项目](../data-tools/media/raddata-import-database-into-database-project.png "raddata 导入数据库到数据库项目")  
  
- 如果您正在创建新数据库，首先将添加**基于服务的数据库文件**到你的项目 (**项目&#124;添加新项)**。 这将创建新的.mdf 文件附加到本地计算机，即默认情况下 (localdb) \MSSQLocalDB 上的默认 SQL Server 实例。 数据库应出现在服务器资源管理器。 展开节点，然后右键单击要添加新的数据库对象，如表、 视图、 函数和等等的节点。  
  
  有关 SQL Server Express LocalDB 的详细信息，请参阅[向 LocalDB 引入、 改进的 SQL Express](http://go.microsoft.com/fwlink/?LinkId=234375)并[LocalDB： 其中，是我的数据库？](http://go.microsoft.com/fwlink/?LinkId=234376) Microsoft 网站上。  
  
  下表提供了介绍如何将应用程序连接到本地数据的主题的链接：  
  
|主题|描述|  
|-----------|-----------------|  
|[使用设计器创建 SQL 数据库](../data-tools/create-a-sql-database-by-using-a-designer.md)|分步介绍如何创建本地数据库文件，可使用该文件测试数据功能并生成应用程序。|  
|[演练：连接到本地数据库文件中的数据（Windows 窗体）](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md)|分步介绍创建简单的 Windows 应用程序时如何连接到 SQL Server Express LocalDB 数据库。|  
|[连接到 Access 数据库中的数据（Windows 窗体）](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)|分步介绍如何连接到 Microsoft Access 数据库。|  
|[如何：连接到 Northwind 数据库](../data-tools/how-to-connect-to-the-northwind-database.md)|介绍如何连接到 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]、SQL Server Compact、SQL Server Express 和 Access 中的 Northwind 示例数据库。|  
  
## <a name="use-the-connection-string"></a>使用连接字符串  
 这是最简单的方法，你的应用程序只是读取数据库，以及时使用第三方数据库是一个不错的选择。 数据库文件可以是位于你的应用程序有权访问，并且数据库系统支持在本地计算机上的任何位置。  
  
1.  （可选）创建新的连接，如中所述[添加新连接](../data-tools/add-new-connections.md)。 对于第三方数据库.mdf 文件，您已知道连接字符串和不会执行数据绑定或使用如 Entity Framework 类或数据集的数据源，此步骤不是必需的。 只需使用连接字符串连接到本地文件。 对于.mdf 文件，请参阅[升级.mdf 文件](../data-tools/upgrade-dot-mdf-files.md)并[建立的连接](https://msdn.microsoft.com/en-us/library/ms254507.aspx)。  
  
2.  （可选）如果使用数据集，Entity Framework 或 LINQ to SQL，然后使用数据源配置向导创建数据源。 有关详细信息，请参阅[添加新数据源](../data-tools/add-new-data-sources.md)。  
  
## <a name="add-an-existing-mdf-to-your-project"></a>向项目添加现有.mdf  
 如果你的应用程序将插入、 删除或更新数据并且你想要保留一份原始文件可用，请考虑将文件添加到你的项目。 时这样做，可以在其上设置项属性**复制到输出目录**到**始终复制**或**如果较新则复制**，并开发应用程序。 生成应用程序，每次原始数据库复制到输出文件夹，并在副本上执行应用程序的更改。 这样一来您始终具有一个干净的原始数据的副本。  
  
1.  使用**Windows 文件资源管理器**拖放的.mdf 文件从其当前位置拖到 Visual Studio 中的解决方案资源管理器中的项目节点。  如果该文件已附加到 localDB 实例，你必须首先分离它。 拖放到项目后，Visual Studio 将自动重新附加它到默认的 localDB 实例。  
  
2.  在新的数据库节点上右键单击并选择属性。 选择复制行为，即**始终复制**或**如果较新则复制**。  
  
## <a name="create-a-sql-server-database-project-and-import-your-database"></a>创建 SQL Server 数据库项目并导入你的数据库  
 当您将会开发数据库本身，可能添加列或表，或更改数据类型时，这是一个不错的选择。  
  
## <a name="each-project-contains-two-copies-of-the-database"></a>每个项目包含数据库的两个副本  
 数据库文件时生成项目时，可能会到输出中，从根项目文件夹将复制**bin**，文件夹。 此行为取决于**复制到输出目录**文件的属性，该属性的默认值取决于正在使用的数据库文件的类型。  
  
 若要查看**bin**中的文件夹**解决方案资源管理器**，选择**显示所有文件**工具栏上的按钮。  
  
> [!NOTE]
>  **复制到输出目录**属性不适用于 web 或 c + + 项目。  
  
 仅当使用编辑数据库架构或数据时更改项目根文件夹中的数据库文件**服务器资源管理器**/**数据库资源管理器**或其他[Visual数据库工具](http://msdn.microsoft.com/en-us/6b145922-2f00-47db-befc-bf351b4809a1)。  
  
 在应用程序开发过程中更改数据时，您要更改的数据库中**bin**文件夹。 例如，选择 F5 键调试应用程序时，就会连接到该文件夹中的数据库。  
  
|值**复制到输出目录**属性|行为|  
|----------------------------------------------------|--------------|  
|**如果较新则复制**（默认值为.sdf 文件）|数据库文件从项目目录复制到**bin** directory 第一次生成项目。 **修改日期**属性文件然后进行比较，每次重新生成项目。 如果项目文件夹中的文件较新，则将其复制到**bin**文件夹，替换以前的文件。 否则，不复制文件。 **注意：** 我们不建议使用此值对于.mdb 或.mdf 文件。 即使数据未更改，数据库文件也可更改。 该文件可以标记为较新，如果您只需打开的连接 (例如，展开**表**中的节点**服务器资源管理器**)。|  
|**始终复制**（默认值为.mdf 和.mdb 文件）|数据库文件从项目目录复制到**bin** directory 生成应用程序每次。 在输出文件夹中对数据文件所做的任何更改都会在下次运行应用程序时被覆盖。|  
|**不复制**|系统从不覆盖的文件中**bin**目录。 你的应用程序会创建指向输出目录中的数据库文件的动态连接字符串。 因此，如果想要输出目录中的数据与项目目录中的数据匹配，必须手动将文件复制到输出目录。|  
  
## <a name="common-issues-with-local-data"></a>与本地数据相关的常见问题  
 下表阐述了使用本地数据文件时可能会遇到的常见问题。  
  
|问题|说明|  
|-----------|-----------------|  
|每次我测试我的应用程序并修改数据后，下次运行此应用程序时我的更改都消失了。|值**复制到输出目录**属性是**如果较新则复制**或**始终复制**。 每次生成项目时，输出文件夹中的数据库（测试应用程序时被修改的数据库）都会被覆盖。 有关详细信息，请参阅[如何： 在您的项目中管理本地数据文件](../data-tools/how-to-manage-local-data-files-in-your-project.md)。|  
|此时会显示一条消息，指明数据文件被锁定。|对于 Access（.mdb 文件）：请验证是否未在其他程序中打开该文件，例如在 Access 中。<br /><br /> 对于 SQL Server Express（.mdf 文件）：如果尝试在 Visual Studio IDE 外部复制、移动或重命名数据文件，SQL Express 会锁定它。|  
|当一个以上用户尝试同时访问同一数据库时，访问会被拒绝。|Visual Studio 利用*用户实例*，这是一项功能的 SQL Server Express 创建每个用户独立的 SQL Server 实例。 在某个用户访问文件后，所有后续用户将无法连接。 例如，因为 IIS 通常是在不同帐户下运行的，如果你尝试同时在 ASP.NET Development Server 和 Internet 信息服务 (IIS) 中运行 Web 应用程序，则可能会出现这种情况。|  
  
## <a name="see-also"></a>请参阅  
 [演练： 连接到本地数据库文件 （Windows 窗体） 中的数据](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md)   
 [连接到 Access 数据库中的数据（Windows 窗体）](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)