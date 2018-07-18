---
title: 处理在 n 层应用程序中的数据集
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- datasets [Visual Basic], n-tier applications
- multi-tier database applications
- DataSet project [VS n-tier applications]
- distributed applications [VS n-tier applications]
- data [Visual Basic], n-tier applications
- TableAdapters, n-tier applications
- n-tier applications
- tiers, n-tier applications
- typed datasets, n-tier applications
- multiple tier applications
ms.assetid: f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: f97e0d4c0cd16fd2bc7cc8bf140a59a800a254ac
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31926110"
---
# <a name="work-with-datasets-in-n-tier-applications"></a>处理在 n 层应用程序中的数据集

*N 层数据应用程序*是以数据为中心的应用程序分成多个逻辑层 (或*层*)。 换句话说，N 层数据应用程序是分离到多个项目中的应用程序，数据访问层、业务逻辑层和表示层都在各自的项目中。 有关详细信息，请参阅[N 层数据应用程序概述](../data-tools/n-tier-data-applications-overview.md)。

类型化数据集经过改进，现在可以在相互独立的项目中生成 TableAdapter 和数据集类。 这使你可以快速分离各应用程序层及生成 N 层数据应用程序。

N 层中类型化数据集的支持可以迭代开发到 n 层设计的应用程序体系结构。它还会删除手动将代码分离到多个项目的要求。 首先，通过使用设计的数据层**数据集设计器**。 如果你已准备好好应用程序体系结构采用 n 层设计，设置**数据集项目**的数据集以在另一个项目中生成数据集类的属性。

## <a name="reference"></a>参考

- <xref:System.Data.DataSet>
- <xref:System.Data.TypedTableBase%601>

## <a name="see-also"></a>请参阅

- [N 层数据应用程序概述](../data-tools/n-tier-data-applications-overview.md)
- [演练：创建 N 层数据应用程序](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [向 N 层应用程序中的 TableAdapter 添加代码](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)
- [向 N 层应用程序的数据集添加代码](../data-tools/add-code-to-datasets-in-n-tier-applications.md)
- [向 N 层数据集添加验证](../data-tools/add-validation-to-an-n-tier-dataset.md)
- [将数据集和 TableAdapter 分离到不同的项目中](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)
- [分层更新](../data-tools/hierarchical-update.md)
- [Visual Studio 中的数据集工具](../data-tools/dataset-tools-in-visual-studio.md)
- [在 Visual Studio 中访问数据](../data-tools/accessing-data-in-visual-studio.md)
- [创建和配置 Tableadapter](../data-tools/create-and-configure-tableadapters.md)
- [使用 LINQ to SQL 的 N 层和远程应用程序](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)