---
title: N 层数据应用程序概述
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- presentation tier
- middle tier
- data tier
- n-tier applications, about n-tier applications
ms.assetid: 1020581d-eaaa-41a2-aca4-bf4c212895f6
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: a47ce13b907d393fae156737a4f20fffe0cddc65
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53907165"
---
# <a name="n-tier-data-applications-overview"></a>N 层数据应用程序概述
*N 层*数据应用程序是数据应用程序，分为多个*层*。 也称为"分布式应用程序"和"多层应用程序"，n 层应用程序分离到相互独立的层的客户端和服务器之间分布处理。 当开发访问数据的应用程序时，应清楚地区分组成应用程序的各个层。

典型的 n 层应用程序包括一个表示层、一个中间层和一个数据层。 单独的 n 层应用程序中的各个层的最简单方法是创建每个层都想要包括在应用程序中的离散项目。 例如，表示层可能是 Windows 窗体应用程序，而数据访问逻辑可以是位于中间层中的类库。 此外，表示层可能与数据访问逻辑在中间层通过服务之类的服务通信。 将应用程序组件分离到不同的层可提高应用程序的可维护性和可伸缩性。 有利于采用新技术，可应用于单个层而无需重新设计整个解决方案执行此操作。 此外，n 层应用程序通常将敏感信息存储在中间层中，以便与表示层隔离。

Visual Studio 包含多种功能，可帮助开发人员创建 n 层应用程序：

-   数据集提供**数据集项目**属性，可用于单独的数据集 （数据实体层） 和 Tableadapter （数据访问层） 相互独立的项目。

-   [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)提供了单独的命名空间中生成的 DataContext 和数据类的设置。 这样，数据访问和数据实体层的逻辑分隔。

-   [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)提供了<xref:System.Data.Linq.Table%601.Attach%2A>方法，可用于从应用程序中的不同层将组合在一起的 DataContext。 有关详细信息，请参阅[N 层和远程应用程序使用 LINQ 到 SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)。

## <a name="presentation-tier"></a>表示层
*表示层*是用户与应用程序交互的层。 它通常还包含其他应用程序逻辑。 典型的表示层组件包括：

-   数据绑定组件，如<xref:System.Windows.Forms.BindingSource>和<xref:System.Windows.Forms.BindingNavigator>。

-   对象表示的数据，例如[LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)表示层中使用的实体类。

表示层通常通过使用服务引用来访问中间层 (例如， [Windows Communication Foundation 服务和 Visual Studio 中的 WCF 数据服务](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)应用程序)。 表示层不直接访问数据层。 表示层与数据层通过中间层中的数据访问组件进行通信。

## <a name="middle-tier"></a>中间层
*中间层*表示层与数据层的层用于相互通信。 典型的中间层组件包括：

-   业务逻辑，例如业务规则和数据验证。

-   数据访问组件和逻辑，如下所示：

    -   [Tableadapter](create-and-configure-tableadapters.md)并[Dataadapter 和 Datareader](/dotnet/framework/data/adonet/dataadapters-and-datareaders)。

    -   对象表示的数据，例如[LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)实体类。

    -   常见的应用程序服务，例如身份验证、 授权和个性化设置。

下图显示了功能和技术，可在 Visual Studio 中以及其中它们可能适合为 n 层应用程序的中间层。

![中间层组件](../data-tools/media/ntiermid.png)中间层

中间层通常可以通过使用数据连接连接到数据层。 此数据连接通常存储在数据访问组件。

## <a name="data-tier"></a>数据层
*数据层*基本上是将应用程序的数据存储 （例如，运行 SQL Server 的服务器） 的服务器。

下图显示了功能和技术，可在 Visual Studio 中以及其中它们可能适合为 n 层应用程序的数据层。

![数据层组件](../data-tools/media/ntierdatatier.png)数据层

不能直接从表示层中的客户端访问的数据层。 相反，中间层中的数据访问组件用于演示文稿和数据层之间的通信。

## <a name="help-for-n-tier-development"></a>关于 n 层开发的帮助
以下主题提供有关使用 n 层应用程序的信息：

[将数据集和 TableAdapter 分离到不同的项目中](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)

[演练：创建 n 层数据应用程序](../data-tools/walkthrough-creating-an-n-tier-data-application.md)

[使用 LINQ to SQL 的 n 层和远程应用程序](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)

## <a name="see-also"></a>请参阅

- [演练：创建 n 层数据应用程序](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [分层更新](../data-tools/hierarchical-update.md)
- [Visual Studio 中的数据集工具](../data-tools/dataset-tools-in-visual-studio.md)
- [在 Visual Studio 中访问数据](../data-tools/accessing-data-in-visual-studio.md)