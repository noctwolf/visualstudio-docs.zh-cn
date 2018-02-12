---
title: "Visual Studio 中的数据科学和分析应用程序工作负载 | Microsoft Docs"
description: "Visual Studio 中的数据科学和分析应用程序工作负载汇集了 Python、R、F# 及其各自的运行时分发版本，包括 Anaconda。"
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
- devlang-python
- devlang-fsharp
ms.tgt_pltfrm: 
ms.topic: landing-page
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: a5ebd00d2eac1b6f8a88a6c3510e822a5eed6734
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="data-science-and-analytical-applications-workload"></a>数据科学和分析应用程序工作负载

通过 Visual Studio 安装程序选择和安装的数据科学和分析应用程序工作负载汇集了三种语言及其各自的运行时分发版本：

- [R 和 Microsoft R Client](../rtvs/index.md)
- [Python 和 Anaconda](../python/overview-of-python-tools-for-visual-studio.md)
- [F# 和 .NET Framework](/dotnet/fsharp/)

![Visual Studio 安装程序中的数据科学和分析应用程序工作负载](media/data-science-workload.png)

R 和 Python 是用于数据科学的两大脚本语言。 这两种语言易于学习，并且有丰富的程序包生态系统提供支持。 这些程序包可应对各种情况，比如数据采集、清理、模型定型、部署和绘制。 F# 还是首款功能强大的 .NET 函数式语言，适用于各种数据处理任务。

<!--Note link on the image because this one is large -->
[![Visual Studio 与 R、Python 和 F# 的屏幕截图](media/data-science-workload-screens.png)](media/data-science-workload-screens.png)

## <a name="workload-options"></a>工作负载选项

该工作负载默认安装以下选项，并且可在 Visual Studio 安装程序中工作负载的摘要部分进行修改：

- F# 语言支持
- Python：
  - Python 语言支持
  - [Anaconda3 64 位](https://www.continuum.io)（Python 分发版本，包含大量数据科学库和一个 Python 解释器）
  - Python Web 支持
  - - Cookiecutter 模板支持
- R:
  - R 语言支持
  - R 开发工具运行时支持
  - [Microsoft R Client](/machine-learning-server/r-client/what-is-microsoft-r-client)（完全兼容、受社区支持且包含多个 ScaleR 库的 Microsoft R 解释器，可加快单个节点或群集上的计算。 也可使用来自 [CRAN](https://cran.r-project.org/) 的任何 R。）

尽管其他许多工作负载附带 F#，Python 也有属于自己的工作负载，但数据科学和分析应用程序仍然是目前唯一一个包含 R 的 工作负载。然而，你也可以不管工作负载，单独安装 R。 在安装程序的“单个组件”选项卡上，选择以下 R 选项：

- “开发活动”>“R 语言支持”
- “开发活动”>“Microsoft R Client”
- “编译器、生成工具和运行时”>“R 开发工具的运行时支持”

## <a name="sql-server-integration"></a>SQL Server 集成

SQL Server 支持使用 R 和 Python 直接在 SQL Server 内执行高级分析。 SQL Server 2016 及更高版本附带 R 支持；SQL Server 2017 CTP 2.0 及更高版本提供 Python 支持。

通过在已包含数据的位置运行代码，可享受许多优点：

- **不必移动数据**：可以在数据库中生成 R 和 Python 应用程序，而不必将数据从数据库移到应用程序或模型。 此功能消除了安全性、合规性、管理和完整性方面的障碍，以及来回移动大量数据导致的一系列类似问题。 还可以使用客户端计算机内存无法容纳的数据集。

- 轻松部署：准备好 R 或 Python 模型后，只需将它嵌入 T-SQL 脚本，即可部署到生产环境。 之后，用任何语言编写的任何 SQL 客户端应用程序就都能通过存储过程调用充分利用这些模型和智能。 无需特定的 R 或 Python 集成。

- **企业级性能和可缩放性**：可将 SQL Server 的内存中表和列存储索引等高级功能与 RevoScaleR 和 RevoScalePy 程序包中的高性能、可缩放 API 结合使用。 不必移动数据还意味着在数据增长或想要提高应用程序性能时不存在客户端内存约束。

- **丰富的扩展性**：可在 SQL Server 中安装和运行任何最新的开源 R 或 Python 程序包，从而基于 SQL Server 中的大量数据生成深入学习和 AI 应用程序。 在 SQL Server 中安装程序包与在本地计算机上安装程序包一样简单。

- **广泛的可用性，且不增加任何成本**：SQL Server 2017 及更高版本的所有版本（包括 Express Edition）均提供 R 和 Python 集成。 （SQL Server 2016 及更高版本提供 R 支持。）

要充分利用 SQL Server 集成，请使用 Visual Studio 安装程序安装具有“SQL Server Data Tools”选项的数据存储和处理工作负载。 后一个选项支持 SQL IntelliSense、语法突出显示和部署。

![数据存储和处理工作负载](media/data-storage-workload.png) &nbsp;&nbsp;&nbsp;&nbsp; ![数据存储和处理工作负载选项](media/data-storage-workload-options.png)

更多相关信息：

- [使用 SQL Server 和 R](../rtvs/sql-server.md)
- [In-database Advanced Analytics with R in SQL Server 2016](https://blogs.technet.microsoft.com/dataplatforminsider/2016/03/29/in-database-advanced-analytics-with-r-in-sql-server-2016/)（在 SQL Server 2016 中利用 R 执行数据库内高级分析）（博客）
- [Python in SQL Server 2017: enhanced in-database machine learning](https://blogs.technet.microsoft.com/dataplatforminsider/2017/04/19/python-in-sql-server-2017-enhanced-in-database-machine-learning/)（SQL Server 2017 中的 Python：增强版数据库内机器学习）（博客）

## <a name="additional-services-and-sdks"></a>其他服务和 SDK

除数据科学和分析应用程序工作负载中的功能外，Azure Notebooks 服务和 Azure SDK for Python 也对数据科学有所助益。

Azure SDK for Python 使得从运行在 Windows、Mac 和 Linux 上的应用程序中使用和管理 Microsoft Azure 服务更加方便。 有关详细信息，请参阅 [Azure SDK for Python](../python/azure-sdk-for-python.md)

Azure Notebooks（当前为预览版）对 Microsoft Azure 云中运行的 Jupyter 笔记本提供免费在线访问。 此服务包括用 Python、R 和 F# 编写的示例笔记本，可帮助用户入门。 请访问 [notebooks.azure.com](https://notebooks.azure.com/)。

<!--Note link on the image because this one is large -->
[![包含 R 简介示例的 Azure Notebooks 屏幕截图](media/data-science-workload-notebooks.png)](media/data-science-workload-notebooks.png)