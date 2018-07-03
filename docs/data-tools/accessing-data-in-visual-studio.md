---
title: 数据访问和工具
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- "80025080"
helpviewer_keywords:
- data [Visual Studio]
- data access [Visual Studio]
- data [C#]
- ADO.NET, data access
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: fbfd4227a2a4acfd8e21703cc29ff13ec36bd986
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="access-data-in-visual-studio"></a>访问 Visual Studio 中的数据

在 Visual Studio 中，你可以创建连接到几乎任何数据库产品或服务，采用何种格式，任何位置中的数据的应用程序 — 在本地计算机上，在本地网络，或在公共、 私有、 或混合云。

对于 JavaScript、 Python、 PHP、 Ruby 或 c + + 中的应用程序，你连接到数据就像任何其他，通过获取库并编写代码。 对于.NET 应用程序，Visual Studio 提供可用于浏览数据源，创建对象模型存储和操作数据在内存中，并将数据绑定到用户界面的工具。 Microsoft Azure 提供适用于连接到 Azure 存储的.NET、 Java、 Node.js、 PHP、 Python、 Ruby，和移动应用和 Visual Studio 中的工具 Sdk。

以下列表显示从 Visual Studio 只是几个可以使用许多数据库和存储系统。 [Microsoft Azure](https://azure.microsoft.com/)产品是数据服务，包括所有设置和管理基础数据存储区。 **Azure 开发**中的工作负荷[Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)使您能够直接从 Visual Studio 的 Azure 数据存储区。

![Azure 开发工作负荷](media/azure-development-workload.png)

可以在本地计算机上，在本地网络上，或在 Microsoft Azure 的虚拟机上托管的其他 SQL 和 NoSQL 数据库产品此处列出的大多数。 如果你承载 Microsoft Azure 虚拟机中的数据库，你负责管理数据库本身。

**Microsoft Azure**

||||
|-|-|-|
|SQL 数据库|Azure Cosmos DB|存储 （blob、 表、 队列、 文件）|
|SQL 数据仓库|SQL Server Stretch Database|StorSimple|

更多内容...

**SQL**

||||
|-|-|-|
|SQL Server 2005-2016，包括 Express 和 LocalDB|Firebird|MariaDB|
|MySQL|Oracle|postgresql|
|SQLite|||

更多内容...

**NoSQL**

||||
|-|-|-|
|Apache Cassandra|CouchDB|MongoDB|
|NDatabase|OrientDB|RavenDB|
|VelocityDB|||

更多内容...

许多数据库供应商和第三方通过 NuGet 包来支持 Visual Studio 集成。 在 nuget.org 上或通过 NuGet 包管理器在 Visual Studio 中，你可以浏览产品 (**工具** > **NuGet 包管理器** > **管理 NuGet解决方案包**)。 其他数据库产品与 Visual Studio 集成扩展。 你可以通过导航到浏览这些产品/服务在 Visual Studio Marketplace**工具**，**扩展和更新**，然后选择**联机**中的左窗格对话框。 有关详细信息，请参阅[for Visual Studio 兼容的数据库系统](../data-tools/installing-database-systems-tools-and-samples.md)。

> [!NOTE]
> 对 SQL Server 2005 的延长的支持已于 2016 年 4 月 12 日结束。 没有数据工具在 Visual Studio 2015 及更高版本将继续使用 SQL Server 2005 在此日期之后能保证。 有关详细信息，请参阅[为 SQL Server 2005 结束支持公告](https://www.microsoft.com/sql-server/sql-server-2005)。

## <a name="net-languages"></a>.NET 语言

所有.NET 数据访问，包括在.NET Core 中都基于 ADO.NET 中，为访问任何类型的数据源、 关系和非关系定义一个接口的一组类。 Visual Studio 具有几个工具和设计器，可使用 ADO.NET 来帮助你连接到数据库，操作数据，并向用户显示数据。 此部分中的文档介绍如何使用这些工具。 你可以直接对 ADO.NET 命令对象进行编程。 有关直接调用 ADO.NET Api 的详细信息，请参阅[ADO.NET](/dotnet/framework/data/adonet/index)。

与 ASP.NET 相关的数据访问文档，请参阅[使用数据](http://www.asp.net/web-forms/overview/presenting-and-managing-data)ASP.NET 站点上。 有关使用使用 ASP.NET MVC 的 Entity Framework 的教程，请参阅[Getting Started with Entity Framework 6 Code First 使用 MVC 5](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/creating-an-entity-framework-data-model-for-an-asp-net-mvc-application)。

在 C# 或 Visual Basic 中的通用 Windows 平台 (UWP) 应用程序可以使用 Microsoft Azure SDK for.NET 来访问 Azure 存储空间和其他 Azure 服务。 Windows.Web.HttpClient 类，可与任何 RESTful 服务的通信。 有关详细信息，请参阅[如何连接到 HTTP 服务器是使用 Windows.Web.Http](https://msdn.microsoft.com/library/windows/apps/dn469430.aspx)。

对于本地计算机上的数据存储，建议的方法是使用 SQLite，在与应用程序相同的进程中运行。 如果需要对象关系映射 (ORM) 层，你可以使用实体框架。 有关详细信息，请参阅[数据访问](/windows/uwp/data-access/index)Windows 开发人员中心中。

如果你要连接到 Azure 服务，请务必下载最新[Azure SDK 工具](https://azure.microsoft.com/downloads/)。

### <a name="data-providers"></a>数据提供程序

要使数据库可以在 ADO.NET 中使用，它必须有一个自定义*ADO.NET 数据提供程序*或其他必须公开一个 ODBC 或 OLE DB 接口。 Microsoft 提供了[ADO.NET 数据提供程序的列表](https://msdn.microsoft.com/data/dd363565)SQL Server 产品以及 ODBC 和 OLE DB 提供程序。

### <a name="data-modeling"></a>数据建模

在.NET 中，你有用于建模和操作在内存中的数据后已从数据源中检索的三个选择：

[实体框架](../data-tools/entity-data-model-tools-in-visual-studio.md)首选的 Microsoft ORM 技术。 你可以使用它到对关系数据的程序作为第一类的.NET 对象。 对于新应用程序，它应为默认的第一个选项，需要一个模型时。 它需要自定义支持的基础的 ADO.NET 提供程序。

[LINQ to SQL](../data-tools/linq-to-sql-tools-in-visual-studio2.md)的更早版本生成的对象关系映射器。 它非常适用于不太复杂的方案，但不再正处于积极开发。

[数据集](../data-tools/dataset-tools-in-visual-studio.md)最旧的三种建模技术。 它主要用于快速开发"forms over data"应用程序在其中你未处理大量数据或执行复杂的查询或转换。 数据集对象包含的数据表和 DataRow 逻辑上而不是.NET 对象更类似于 SQL 数据库对象的对象。 对于基于 SQL 数据源相对简单的应用程序，数据集可能仍是一个不错的选择。

没有无需使用任何一种技术。 在某些情况下，尤其是在性能非常重要，你可以只需使用 DataReader 对象从数据库读取，并将你所需的值复制到一个集合对象，如列表\<T >。

## <a name="native-c"></a>本机 C++

连接到 SQL Server 的 c + + 应用程序应使用[Microsoft® ODBC Driver 13.1 for SQL Server](https://www.microsoft.com/download/details.aspx?id=53339)在大多数情况下。 如果链接服务器，则是必需的 OLE DB 和为此你使用[SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client)。 你可以通过使用访问其他数据库[ODBC](https://msdn.microsoft.com/library/ms710252\(v=vs.85\).aspx)或 OLE DB 驱动程序直接。 ODBC 是当前的标准数据库接口，但大多数数据库系统提供无法通过 ODBC 接口访问的自定义功能。 OLE DB 是一项传统 COM 数据访问技术仍受支持但不建议用于新应用程序。 有关详细信息，请参阅[Visual c + + 中的数据访问](/cpp/data/data-access-in-cpp)。

使用 REST 服务的 c + + 程序可以使用[c + + REST SDK](https://github.com/Microsoft/cpprestsdk)。

使用 Microsoft Azure 存储空间的 c + + 程序可以使用[Microsoft Azure 存储客户端](http://www.nuget.org/packages/wastorage)。

数据建模&mdash;Visual Studio 不提供针对 c + + 的 ORM 层。 [ODB](http://www.codesynthesis.com/products/odb/)流行的开放源代码 ORM 为 c + +。

若要了解有关从 c + + 应用连接到数据库的详细信息，请参阅[用于 c + + 的 Visual Studio data tools](../data-tools/visual-studio-data-tools-for-cpp.md)。 有关以前的 Visual c + + 数据访问技术的详细信息，请参阅[数据访问](/cpp/data/data-access-in-cpp)。

## <a name="javascript"></a>JavaScript

[Visual Studio 中的 JavaScript](/scripting/javascript/javascript-language-reference)是用于构建跨平台应用、 UWP 应用、 云服务、 网站和 web 应用的一级语言。 可以使用 Bower、 Grunt、 Gulp、 npm 和从 Visual Studio 中的 NuGet 安装你最喜欢的 JavaScript 库和的数据库产品。 连接到 Azure 存储空间和服务通过下载 Sdk 从[Azure 网站](https://azure.microsoft.com/)。 Edge.js 是连接到 ADO.NET 数据源的服务器端 JavaScript (Node.js) 的库。

## <a name="python"></a>Python

安装[Visual Studio 中的 Python 支持](../python/overview-of-python-tools-for-visual-studio.md)创建 Python 应用程序。 Azure 文档具有连接到数据，包括以下几个教程：

- [Django 和在 Azure 上的 SQL 数据库](/azure/app-service/app-service-web-get-started-python)
- [Django 和在 Azure 上的 MySQL](/azure/app-service-web/web-sites-python-ptvs-django-mysql)
- 使用[blob](/azure/storage/blobs/storage-quickstart-blobs-python)，[文件](/azure/storage/files/storage-python-how-to-use-file-storage)，[队列](/azure/storage/queues/storage-python-how-to-use-queue-storage)，和[表 (Cosmo DB)](/azure/cosmos-db/table-storage-how-to-use-python)。

## <a name="related-topics"></a>相关主题

[Microsoft AI 平台](https://azure.microsoft.com/overview/ai-platform/?v=17.42w)&mdash;提供对 Microsoft 智能云，包括 Cortana Analytics Suite 和物联网的支持的介绍。

[Microsoft Azure 存储空间](/azure/storage/)&mdash;介绍 Azure 存储空间，以及如何使用 Azure blob、 表、 队列和文件创建应用程序。

[Azure SQL 数据库](/azure/sql-database/)&mdash;介绍如何连接到 Azure SQL 数据库，关系数据库即服务。

[SQL Server Data Tools](/sql/ssdt/download-sql-server-data-tools-ssdt)&mdash;介绍简化设计，浏览、 测试和部署的数据连接的应用程序和数据库的工具。

[ADO.NET](/dotnet/framework/data/adonet/index)&mdash;描述 ADO.NET 结构以及如何使用 ADO.NET 类来管理应用程序数据并与数据源和 XML 进行交互。

[ADO.NET 实体框架](https://msdn.microsoft.com/data/ef)&mdash;描述如何创建允许开发人员对概念模型而不是直接针对关系数据库编程的数据应用程序。

[WCF 数据服务 4.5](/dotnet/framework/data/wcf/index)&mdash;介绍如何使用[!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]部署 web 或 intranet 上的数据服务实现[开放数据协议 (OData)](http://go.microsoft.com/fwlink/?LinkID=182204)。

[Office 解决方案中的数据](../vsto/data-in-office-solutions.md)&mdash;包含指向这些主题介绍了数据在 Office 解决方案中的工作方式。 这包括有关面向架构的编程、 数据缓存和服务器端数据访问的信息。

[LINQ （语言集成查询）](/dotnet/csharp/linq/)&mdash;描述内置于 C# 和 Visual Basic 和查询关系数据库、 XML 文档、 数据集和内存中集合的常见模型的查询功能。

[Visual Studio 中的 XML 工具](../xml-tools/xml-tools-in-visual-studio.md)&mdash;讨论 XML 数据，调试 XSLT，.NET Framework XML 功能，使用和 XML 查询的体系结构。

[XML 文档和数据](/dotnet/standard/data/xml/index)&mdash;概述了对全面、 集成的一组处理 XML 文档和.NET Framework 中的数据的类。
