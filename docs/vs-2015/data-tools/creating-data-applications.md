---
title: 创建数据应用程序 |Microsoft Docs
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
- data access [Visual Studio], creating applications
- applications [Visual Studio], data
- data [Visual Studio]
- data [Visual Studio], creating applications
ms.assetid: ab334d5f-4f49-4346-bce0-3325d6130b3e
caps.latest.revision: 41
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 4e5354d167dd6d3a1bef9beeb3dcaaaf24871bab
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49291301"
---
# <a name="creating-data-applications"></a>创建数据应用程序
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 提供许多设计时工具，可帮助你创建访问数据的应用程序。 本文概述了创建数据处理应用程序所涉及的基本过程。 此处的信息有意略过了许多细节，其设计目的是提供一个一般信息来源和起点，读者可借此访问与创建数据应用程序有关的很多其他帮助页。  
  
 在 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中开发数据访问应用程序时的需求不尽相同。 在某些情况下，可能只是想在窗体上显示数据。 而在另一些情况下，则可能需要设计出一种方法，以与其他应用程序或过程共享信息。  
  
 无论对数据做何处理，你都应该清楚一些基本概念。 你可能从不需要了解数据处理的某些细节（例如，你可能从不需要以编程方式创建数据库），但是了解基本数据概念以及 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中提供的数据工具（向导和设计器）将非常有用。  
  
 一个典型的数据应用程序会使用下图中所示的大部分过程：  
  
 ![数据循环图](../data-tools/media/datacyclegraphicinfo.gif "datacyclegraphicinfo")  
数据循环  
  
 在你创建应用程序时，请考虑要完成什么样的任务。 使用以下各节来帮助查找你可使用的 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 工具和对象。  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 提供向导来简化上图中显示的若干过程。 例如，运行**数据源配置向导**提供足够的信息来连接到数据、 创建类型化数据集来接收数据，并将数据导入你的应用程序与应用程序。  
  
 若要快速查看如何[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]可帮助你开发数据应用程序，请参阅[演练： 创建简单的数据应用程序](http://msdn.microsoft.com/library/c5d0968c-d86f-4ae9-a2e1-871f208a3bb3)。  
  
## <a name="connecting-to-data"></a>连接到数据  
 为了将数据引入应用程序（并将更改发回数据源），需要建立某种双向通信机制。 这种双向通信通常由数据模型中的对象进行处理。  
  
 例如，`TableAdapter` 将使用数据集的应用程序连接到数据库，<xref:System.Data.Objects.ObjectContext> 将实体框架中的实体连接到数据库。 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 提供了多种工具来帮助创建应用程序可使用的连接。 连接到数据的应用程序的详细信息，请参阅[连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)。  
  
 若要了解如何使用数据集应用程序连接到数据库中的数据，请参阅[演练： 连接到数据库 （Windows 窗体） 中的数据](http://msdn.microsoft.com/library/02d39aa6-8993-4602-be13-a13536af3d1c)。  
  
## <a name="preparing-your-application-to-receive-data"></a>准备应用程序以接收数据  
 如果应用程序使用断开连接的数据模型，则在使用数据时需要临时将数据存储在应用程序中。 Visual Studio 提供的工具可帮助你创建应用程序用于临时存储数据的对象：数据集、实体和 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 对象。  
  
> [!NOTE]
>  使用断开连接的数据模型的应用程序通常执行以下过程：连接到数据库、运行将数据引入应用程序的查询、断开与数据库的连接、脱机操作数据，然后重新连接并更新数据库。  
  
 在应用程序中创建类型化数据集的详细信息，请参阅[准备您的应用程序对接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)。 在 n 层应用程序中使用数据集的其他信息，请参阅[分隔到不同的项目的数据集和 Tableadapter](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)。  
  
 若要了解如何创建数据集，请完成中的过程[演练： 使用数据集设计器创建数据集](../data-tools/walkthrough-creating-a-dataset-with-the-dataset-designer.md)。  
  
 若要了解如何创建[!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)]对象，请完成中的过程[演练： 创建 LINQ to SQL 类 （O-R 设计器）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)。  
  
## <a name="fetching-data-into-your-application"></a>将数据提取到你的应用程序  
 无论应用程序是否使用断开连接的数据模型，你都需要将数据取入应用程序。 通过对数据库执行查询或存储过程可将数据引入应用程序。 将数据存储在数据集的应用程序通过使用执行查询和存储的过程`TableAdapter`s，而在实体中存储数据的应用程序使用执行查询[LINQ to Entities](http://msdn.microsoft.com/library/641f9b68-9046-47a1-abb0-1c8eaeda0e2d)或通过连接实体直接向存储过程。 有关创建和编辑使用 Tableadapter 的查询的详细信息，请参阅[如何： 创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)并[如何： 编辑 TableAdapter 查询](../data-tools/how-to-edit-tableadapter-queries.md)。  
  
 有关数据加载到数据集，以及有关正在执行的查询和存储的过程的详细信息，请参阅[将数据提取到您的应用程序](../data-tools/fetching-data-into-your-application.md)。  
  
 若要了解如何将数据加载到数据集，请完成中的过程[演练： 在 Windows 窗体上显示数据](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)并检查窗体加载事件处理程序中的代码。  
  
 若要了解如何将数据加载到[!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)]对象，请完成中的过程[演练： 创建 LINQ to SQL 类 （O-R 设计器）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)。  
  
 若要了解如何创建和执行 SQL 查询，请参阅[如何： 创建和执行 SQL 语句，返回的行](http://msdn.microsoft.com/library/14637fc5-d42a-4cca-97ac-54c181ec3eed)。  
  
 若要了解如何执行存储的过程，请参阅[如何： 执行存储过程的返回行](http://msdn.microsoft.com/library/db3d7021-d3ef-4db8-b12a-b6146570355d)。  
  
## <a name="displaying-data-on-forms"></a>在窗体上显示数据  
 将数据引入应用程序后，你通常将数据显示在窗体上以供用户查看或修改。 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 提供了[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)，其中您可以将项拖到窗体中自动创建显示数据的数据绑定控件。 数据绑定和向用户显示数据的详细信息，请参阅[将控件绑定到 Visual Studio 中的数据](../data-tools/bind-controls-to-data-in-visual-studio.md)。  
  
 若要了解如何向用户提供数据，请完成以下演练中的过程 (特别注意的将某些项从过程**数据源**窗口):  
  
-   [演练： 在 Windows 窗体上显示数据](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)。  
  
-   [将 WPF 控件绑定到 WCF 数据服务](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)  
  
-   [演练： 将 Silverlight 控件绑定到 WCF 数据服务](http://msdn.microsoft.com/library/f3f08661-7d91-4185-8ed6-912d524d4c6b)  
  
## <a name="editing-data-in-your-application"></a>在应用程序中编辑数据  
 向用户显示数据后，用户可能会通过添加新记录、编辑和删除记录等操作修改数据，然后将数据发回数据库。  
  
 使用的数据加载到你的数据集后的详细信息，请参阅[在应用程序中编辑数据](../data-tools/editing-data-in-your-application.md)。  
  
## <a name="validating-data"></a>验证数据  
 更改数据时，你一般希望先检验一下所做的更改，然后决定是否允许在数据集中接受更改后的值，以及是否将更改后的值写入数据库。 *验证*是过程的名称检验这些新值是否符合你的应用程序的要求。 可以在应用程序中添加逻辑以便在值发生变化时检查这些值。 Visual Studio 提供的工具可帮助你添加代码，以用于在列和行发生变化时验证数据。 有关详细信息，请参阅[验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)。  
  
 若要了解如何将数据验证添加到你的应用程序，请参阅[演练： 向数据集添加验证](http://msdn.microsoft.com/library/09351fab-d670-45e3-b53a-a944eff717e7)。  
  
 若要了解如何将验证添加到被分隔为 n 层应用程序的数据集，请参阅[向 n 层数据集添加验证](../data-tools/add-validation-to-an-n-tier-dataset.md)。  
  
## <a name="saving-data"></a>保存数据  
 在应用程序中做出并验证更改后，通常要将所做更改发回数据库。 将数据存储到数据集的应用程序通常使用 TableAdapterManager 保存数据。 有关详细信息，请参阅[TableAdapterManager 概述](http://msdn.microsoft.com/library/33076d42-6b41-491a-ac11-6c6339aea650)。 实体框架应用程序使用<xref:System.Data.Objects.ObjectContext.SaveChanges%2A>方法来保存数据。  
  
 有关将更新后的数据发送回数据库的详细信息，请参阅[保存数据](../data-tools/saving-data.md)。  
  
 若要了解如何将更新后的数据从数据集发送到数据库，请完成中的过程[演练： 保存相关数据表 （分层更新） 中的数据](http://msdn.microsoft.com/library/50601bd7-a488-480c-9910-3c6570fa3a1b)。  
  
## <a name="related-topics"></a>相关主题  
 [Visual Studio 的数据应用程序概述](../data-tools/overview-of-data-applications-in-visual-studio.md)  
 提供相关主题的链接，这些主题介绍如何创建处理数据的应用程序。  
  
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)  
 提供指向有关如何使用主题[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]应用程序连接到数据并创建你的应用程序的数据源。  
  
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)  
 提供相关主题的链接，这些主题介绍如何在应用程序中使用数据模型（包括数据集和实体数据模型）。  
  
 [将数据提取到应用程序中](../data-tools/fetching-data-into-your-application.md)  
 提供相关主题的链接，这些主题介绍如何将数据加载到应用程序中。  
  
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)  
 提供相关主题的链接，这些主题介绍如何将 Windows 窗体控件、WPF 控件和 Silverlight 控件绑定到数据源。  
  
 [在应用程序中编辑数据](../data-tools/editing-data-in-your-application.md)  
 提供相关主题的链接，这些主题介绍如何在应用程序中更改数据。  
  
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)  
 提供相关主题的链接，这些主题介绍如何向数据更改中添加验证。  
  
 [保存数据](../data-tools/saving-data.md)  
 提供相关主题的链接，这些主题介绍如何将已更新的数据从应用程序发送到数据库，或如何将数据保存为诸如 XML 等其他格式。  
  
 [使用 Visual Studio 中的数据源的工具](http://msdn.microsoft.com/library/1e584c75-900a-49a0-a82a-d19172ef2eb3)  
 提供指向有关工具可用于使用数据源在 Visual Studio 中，如主题**数据源**窗口和 ADO.NET 实体数据模型设计器。