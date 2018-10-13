---
title: 如何： 连接到数据库中的数据 |Microsoft Docs
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
- databases, connecting to
- data sources, databases
- data [Visual Studio], connecting to databases
- data sources, creating
- database connections
ms.assetid: 6c56e54e-8834-4297-85aa-cc1a443ba556
caps.latest.revision: 55
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: e75de3c81270449da6fe6bb504b476b912f51583
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49273801"
---
# <a name="how-to-connect-to-data-in-a-database"></a>如何：连接到数据库中的数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

你可以使用 Visual Studio 将应用程序连接到数据库。 创建数据连接后，Visual Studio 将生成一个数据模型，应用程序将使用该数据模型与数据库中的数据交互。 数据模型中的对象出现在[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)。 然后可以通过将项从创建数据绑定控件**数据源窗口**到设计图面。 有关详细信息，请参阅[将控件绑定到 Visual Studio 中的数据](../data-tools/bind-controls-to-data-in-visual-studio.md)。  
  
 本主题提供有关连接到数据库和创建以下类型的数据模型的说明：  
  
-   数据集  
  
-   实体数据模型 (EDM)  
  
> [!NOTE]
>  也可以使用 Visual Studio 通过数据库创建 LINQ to SQL 类。 但是，LINQ to SQL 类不显示在**数据源**窗口中，因此不能将它们拖到设计器中创建数据绑定控件直接。 有关创建 LINQ to SQL 类从数据库的详细信息，请参阅[如何： 创建 LINQ to SQL 类映射到表和视图 （O/R 设计器）](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
##  <a name="dataset"></a> 连接到数据库并创建数据集  
 当你创建基于数据库的数据集时，Visual Studio 将创建一组表示数据的可编程视图的类。 主类称为*类型化数据集*。 类型化数据集包含表示数据库中的表的数据表对象。 有关类型化数据集的详细信息，请参阅[Visual Studio 中的数据集工具](../data-tools/dataset-tools-in-visual-studio.md)。  
  
 创建数据集后，你可以通过将数据集对象从“数据源”窗口拖到 WPF 或 Windows 窗体设计器来创建数据绑定 WPF 或 Windows 窗体控件。  
  
#### <a name="to-connect-your-application-to-a-database-and-create-a-dataset"></a>将应用程序连接到数据库并创建数据集  
  
1.  在 Visual Studio 中打开一个现有项目，或创建一个新项目。  
  
2.  在 **“数据”** 菜单上，单击 **“添加新数据源”**。  
  
     **数据源配置向导**随即打开。  
  
3.  上**选择数据源类型**页上，选择**数据库**，然后单击**下一步**。  
  
4.  上**选择数据库模型**页上，选择**数据集**，然后单击**下一步**。  
  
5.  上**选择数据连接**页上，从可用连接列表中选择一个数据连接，然后单击**下一步**。  
  
     如果所需的数据连接不可用，按照中的步骤创建新的连接[创建新的数据库连接](#CreatingDataConnection)。  
  
6.  上**将连接字符串保存到应用程序配置文件**页上，根据需要清除**是，保存所用连接**复选框，如果你想要直接在编译中保存连接字符串应用程序。 默认情况下，连接保存在应用程序配置文件中。 有关详细信息，请参阅[如何： 保存和编辑连接字符串](~/E:/Repos/visualstudio-docs-pr/docs/data-tools/how-to-save-and-edit-connection-strings.md)。  
  
7.  上**选择数据库对象**页上，选择将在你的应用程序中使用的数据库对象。 此外可以选择替换默认**数据集名称**。  
  
8.  单击 **“完成”**。 只需创建的数据集现已推出**数据源**窗口。  
  
    > [!NOTE]
    >  如果**数据源**窗口未打开，请单击**显示数据源**上**数据**菜单以打开窗口。  
  
9. 现在可以将项从**数据源**到 WPF 设计器中，Windows 窗体设计器中，窗口或[Component Designer](http://msdn.microsoft.com/library/61a3a450-5b15-465e-bd9a-72a6c8c2b282)来创建数据绑定控件。 有关详细信息，请参阅[将控件绑定到 Visual Studio 中的数据](../data-tools/bind-controls-to-data-in-visual-studio.md)。  
  
##  <a name="edm"></a> 连接到数据库并创建实体数据模型  
 当你创建基于数据库的实体数据模型时，Visual Studio 将创建一组表示数据的可编程视图的类。 有关实体数据模型和 ADO.NET 实体框架的详细信息，请参阅[实体框架概述](http://msdn.microsoft.com/library/a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0)。  
  
 创建实体数据模型后，你可以通过将实体对象从“数据源”窗口拖到 WPF 设计器来创建数据绑定 WPF 控件。  
  
#### <a name="to-connect-your-application-to-a-database-and-create-an-entity-data-model"></a>将应用程序连接到数据库并创建实体数据模型  
  
1.  在 Visual Studio 中打开一个现有项目，或创建一个新项目。  
  
2.  按照中的步骤**实体数据模型向导**以连接到数据库并指定模型的内容。 有关详细信息，请参阅[如何： 创建新的.edmx 文件](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2)。  
  
3.  完成后**实体数据模型向导**、 在实体数据模型设计器中打开您创建的实体数据模型和数据对象现在均可在**数据源**窗口。  
  
    > [!NOTE]
    >  如果**数据源**窗口未打开，请单击**显示数据源**上**数据**菜单以打开窗口。  
  
4.  如果 WPF 设计器打开，您现在可以将项从**数据源**到设计器来创建绑定到实体数据模型的控件的窗口。 有关详细信息，请参阅[控件添加到 Visual Studio 中的数据绑定 WPF](../data-tools/bind-wpf-controls-to-data-in-visual-studio2.md)。  
  
     如果 Windows 窗体设计器打开，无法将项从**数据源**到设计器。 若要创建绑定到实体数据模型的控件，你必须生成项目，添加基于实体数据模型的新对象数据源，然后将这些对象拖到设计器。  
  
##  <a name="CreatingDataConnection"></a> 创建新的数据库连接  
 当你使用**数据源配置向导**或**实体数据模型向导**，必须指定与你想要使用的数据库的连接。 如果还没有数据库连接，请执行以下步骤创建连接。  
  
 这些说明假定你已开始**数据源配置向导**或**实体数据模型向导**中所述[连接到数据库并创建一个数据集](#dataset)并[连接到数据库并创建实体数据模型](#edm)。  
  
#### <a name="to-create-a-new-database-connection"></a>创建新数据库连接  
  
1.  上**选择数据连接**页**数据源配置向导**或**实体数据模型向导**，单击**新连接**.  
  
     将进行以下操作之一：  
  
    -   如果已在 Visual Studio 中，创建数据连接**添加连接**对话框随即打开。  
  
    -   如果这是已在 Visual Studio 中创建的第一个数据连接**选择数据源**对话框显示。 选择你想要连接的对象，然后单击的数据库的类型**确定**以显示**添加连接**对话框。  
  
2.  在中**添加连接**对话框框中，输入所需的信息。 **添加连接**对话框是不同的每种类型的数据提供程序。  
  
    > [!NOTE]
    >  如果所选**数据源**中**添加连接**对话框的不是你想要连接到，请单击数据源**更改**以打开**变更数据源**对话框框，然后选择不同的数据源。  
  
3.  在中**添加连接**对话框中，单击**确定**。  
  
     返回到**选择数据连接**页**数据源配置向导**或**实体数据模型向导**。  
  
4.  上**选择数据连接**页上，请确保新的数据连接处于选定状态，然后单击**下一步**。  
  
5.  完成剩余步骤**数据源配置向导**或**实体数据模型向导**。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 存储敏感信息（如密码）会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅[保护连接信息](http://msdn.microsoft.com/library/1471f580-bcd4-4046-bdaf-d2541ecda2f4)。  
  
## <a name="see-also"></a>请参阅  
 [添加新数据源](../data-tools/add-new-data-sources.md)   
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [连接到数据源](http://msdn.microsoft.com/library/9abc3f92-1be3-4e1a-b360-762dc689650e)