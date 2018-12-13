---
title: 编辑 Tableadapter |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.datasource.dbtablefunctionwizard
- vs.datasource.datacomponentquerywizard
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], data component queries
- data [Visual Studio], TableAdapters
- TableAdapter Query Configuration Wizard
- data [Visual Studio], table adapter queries
ms.assetid: 8c06b306-24d0-4521-948d-07e3b7badd95
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: b242f8154f31391d168f2a41bfd00c01f037d87e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49877642"
---
# <a name="editing-tableadapters"></a>编辑 Tableadapter
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

有时你可能想要更改适配器的表的架构。 若要执行此操作，您可以修改适配器的主`Fill`方法。 用一个 main 创建 Tableadapter`Fill`方法，用于定义关联的数据的表的架构。 主`Fill`方法基于查询或存储的过程输入您在最初配置 TableAdapter 时; 它是数据表的第一个 （最顶部） 方法上[创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)。  
  
 ![使用多个查询的 TableAdapter](../data-tools/media/tableadapter.gif "TableAdapter")  
  
 向 TableAdapter 所做的任何更改的主`Fill`方法将反映在关联的数据的表的架构中。 例如，从主查询中删除列`Fill`方法将同时删除关联的数据表格中的列。 此外，从 main 中删除该列`Fill`方法移除列从任何其他查询的 TableAdapter。  
  
 可以使用**TableAdapter 查询配置向导**来创建和编辑其他查询的 TableAdapter。 这些附加的查询必须符合表架构，除非它们返回一个标量值。  其他查询具有你指定的名称 (例如， `CustomersTableAdapter.FillByCity(NorthwindDataSet.Customers, "Seattle")`。)  
  
#### <a name="to-start-the-tableadapter-query-configuration-wizard-with-a-new-query"></a>若要开始使用新查询的 TableAdapter 查询配置向导  
  
1.  打开中的数据集**数据集设计器**。  
  
2.  如果要创建一个新的查询，请拖动**查询**对象从**数据集**选项卡**工具箱**拖到<xref:System.Data.DataTable>，或选择**添加查询**TableAdapter 的快捷菜单中。 您还可以拖动**查询**对象拖放到的空白区域**数据集设计器**，这将创建没有关联的 TableAdapter <xref:System.Data.DataTable>。 这些查询是限于返回单个值 （标量），或执行 UPDATE、 INSERT 或 DELETE 针对数据库的命令。 有关详细信息，请参阅[如何： 向 TableAdapter 添加全局查询](../data-tools/how-to-add-global-queries-to-a-tableadapter.md)。  
  
3.  上**选择数据连接**页上，选择或创建查询要使用的连接。  
  
    > [!NOTE]
    >  当在设计器无法确定正确的连接，若要使用，或没有连接可用时，才会显示此页。  
  
4.  上**选择命令类型**页上，从以下方法从数据库提取数据的选择：  
  
    -   **使用 SQL 语句**，可键入 SQL 语句，以便从您的数据库选择的数据。  
  
    -   **创建新的存储的过程**— 选择此选项以让向导创建新的存储的过程 （在数据库中） 根据指定的 SELECT 语句。  
  
    -   **使用现有存储的过程**— 选择此选项以运行查询时执行现有的存储的过程。  
  
#### <a name="to-start-the-tableadapter-query-configuration-wizard-on-an-existing-query"></a>若要启动 TableAdapter 查询配置向导在现有的查询  
  
-   如果正在编辑现有 TableAdapter 查询，右键单击查询，然后选择**配置**从快捷菜单。  
  
    > [!NOTE]
    >  右键单击 TableAdapter 的主查询重新配置 TableAdapter 和<xref:System.Data.DataTable>架构中，右键单击 TableAdapter 上的其他查询而仅可配置所选的查询。 **TableAdapter 配置向导**重新配置 TableAdapter 定义; **TableAdapter 查询配置向导**重新配置选定的查询。  
  
## <a name="running-the-wizard"></a>运行向导  
 将查询拖动到**数据集设计器**，或配置现有查询 （第一个查询下面列出的任何查询）。  
  
 TableAdapter 中的第一个查询是 TableAdapter 的主查询。 编辑此主查询将打开**TableAdapter 配置向导**和编辑 TableAdapter 的数据表的架构。 主查询下面列出的所有查询均为附加查询并使用配置**TableAdapter 查询配置向导**。 运行向导的详细信息，请参阅[如何： 启动 TableAdapter 查询配置向导](http://msdn.microsoft.com/library/fc7b468e-3417-48a4-a8aa-cace8f99c24a)。  
  
## <a name="choose-your-data-connection"></a>选择你的数据连接  
 从连接列表中选择一个现有的连接，或单击**新的连接**若要创建与你的数据库的连接。  
  
 完成后**连接属性**对话框中，**连接详细信息**区域显示有关所选提供程序，以及连接字符串的只读信息。  
  
## <a name="save-the-connection-string-to-the-application-configuration-file"></a>将连接字符串保存到应用程序配置文件中  
 选择**是，保存所用连接**连接字符串存储在应用程序配置文件中。 为连接键入名称或使用提供的默认名称。  
  
 将连接字符串保存在应用程序配置文件中可简化数据库连接更改时的应用程序维护过程。 当数据库连接发生更改时，可以在应用程序配置文件中编辑连接字符串。 这样，就不必编辑源代码和重新编译应用程序。 编辑应用程序配置文件中的连接字符串的信息，请参阅[如何： 保存和编辑连接字符串](~/E:/Repos/visualstudio-docs-pr/docs/data-tools/how-to-save-and-edit-connection-strings.md)。  
  
> [!IMPORTANT]
>  信息以纯文本格式存储在应用程序配置文件中。 为了减少对敏感信息进行未授权访问的可能性，你可能需要加密数据。 有关详细信息，请参阅[加密和解密数据](http://msdn.microsoft.com/en-us/22812ae8-e082-4eb1-a29b-21b6ee00c6b5)。  
  
## <a name="use-sql-statements"></a>使用 SQL 语句  
 本部分介绍如何完成**TableAdapter 查询配置向导**选择时**使用 SQL 语句**选项。  
  
## <a name="choose-a-query-type"></a>选择查询类型  
 根据应用程序的要求，该向导可创建几种类型的查询。 你可以选择返回数据行（数据表）的 SELECT 查询，也可以选择返回标量值（单个值，如 `Count` 或 `Sum`）的 SELECT 查询。  
  
 上**选择查询类型**页上，选择要从可用查询列表创建查询的类型。  
  
> [!NOTE]
>  创建 INSERT、UPDATE 或 DELETE 语句不会替换调用 TableAdapter 的 `Update` 方法时所使用的 TableAdapter 命令。 例如，将 UPDATE 选为查询类型将创建一个新查询，其名称将在向导的后续步骤中指定。 通过调用 TableAdapter 的这一命名方法，可执行此查询。 调用 TableAdapter 的 `Update` 方法将执行在最初配置 TableAdapter 时所创建的语句。  
  
## <a name="specify-a-sql-query-type-statement"></a>指定 SQL\<查询类型 > 语句  
 上**指定 SQL 语句**页上，键入要在调用该查询时执行的 SQL 语句。  
  
> [!TIP]
>  该向导提供对访问**查询生成器**，一个用于创建 SQL 查询的可视化工具。 若要打开它，请单击**查询生成器**按钮。  
  
## <a name="choose-methods-to-generate"></a>选择要生成的方法  
 此页面提供了用于选择向导为查询生成哪些方法的选项。  
  
 **填充 DataTable**  
 创建用于填充数据表的方法。 当调用此方法以使用返回的数据填充数据表时，需要将数据表的名称作为参数进行传递。  
  
 （可选） 可以更改中的默认名称**方法名称**框。 当以代码形式处理此查询时，提供一个有意义的名称会很有帮助。  
  
 **返回 DataTable**  
 创建用于返回已填充数据表的方法。 在某些应用程序中，更多的是需要返回已填充的数据表，而不是使用数据填充现有数据表。  
  
 （可选） 可以更改中的默认名称**方法名称**框。  
  
## <a name="choose-function-name"></a>选择函数名  
 键入函数的名称。 创建 TableAdapter 查询会将一个方法添加到具有此处所提供名称的 TableAdapter 中。 调用此方法以执行查询。 当以代码形式处理此查询时，提供一个有意义的名称会很有帮助。  
  
> [!NOTE]
>  创建新存储过程时，系统会要求你提供两个名称。 第一个名称是在数据库中创建的存储过程的名称；第二个名称是在被调用时执行存储过程的 TableAdapter 上的方法的名称。  
  
## <a name="create-new-stored-procedures"></a>创建新存储过程  
 本部分介绍如何完成**TableAdapter 查询配置向导**选择时**创建新的存储的过程**选项。  
  
1. 在中**生成存储过程**页上，键入要在调用存储的过程时执行的 SQL 语句。  
  
   > [!NOTE]
   >  该向导提供对访问**查询生成器**，一个用于创建 SQL 查询的可视化工具。 若要打开它，请单击**查询生成器**按钮。  
  
2. 在中**创建存储的过程**页上，执行以下操作：  
  
   1. 为新存储过程键入名称。  
  
   2. 指定是否在基础数据库中创建存储过程。  
  
      > [!NOTE]
      >  在数据库中创建存储过程的能力由特定数据库的安全设置所决定。  
  
      **查看向导结果**页显示了创建 TableAdapter 查询的结果。 如果向导遇到问题，此屏幕会提供错误信息。  
  
## <a name="use-existing-stored-procedures"></a>使用现有存储过程  
 本部分介绍如何完成**TableAdapter 查询配置向导**选择时**使用现有存储的过程**选项。  
  
1.  在选择下拉列表从现有的存储的过程**选择一个现有的存储的过程**向导页。  
  
     **参数**并**结果**所选存储过程显示的引用。  
  
2.  单击 **“下一步”**。  
  
## <a name="choose-the-shape-of-data-returned-by-the-stored-procedure"></a>选择由存储过程返回的数据的形式  
 由选定存储过程返回的数据类型决定该向导创建 TableAdapter 方法的方式。  
  
 选择由此查询返回的数据类型。  
  
-   选择**表格数据**会打开**生成的选择方法**页 （如前文所述此帮助页），它允许您指定的方法、 方法名称和要创建的分页支持的类型。  
  
-   选择**单个值**创建返回单个值的类型化的方法。 此选项可打开**选择函数名**页面 （请参见此帮助页前面的说明）。  
  
-   选择**没有值**创建执行存储的过程，并期望没有要返回的数据的类型化的方法。 此选项可打开**选择函数名**页面 （请参见此帮助页前面的说明）。  
  
## <a name="view-wizards-results"></a>查看向导结果  
 **查看向导结果**页显示了创建 TableAdapter 查询的结果。 如果该向导遇到问题，则会在此页面上显示详细信息。  
  
## <a name="see-also"></a>请参阅  
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)   
 [如何： 编辑 TableAdapter 查询](../data-tools/how-to-edit-tableadapter-queries.md)   
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [在 Visual Studio 中的数据应用程序的概述](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)