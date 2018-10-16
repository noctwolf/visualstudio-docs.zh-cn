---
title: 用 TableAdapter DBDirect 方法保存数据 |Microsoft Docs
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
- TableAdapters, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], TableAdapter
ms.assetid: 74a6773b-37e1-4d96-a39c-63ee0abf49b1
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6bb326f1cad6ea019c5d057ca24d198c28dca2a6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49220802"
---
# <a name="save-data-with-the-tableadapter-dbdirect-methods"></a>用 TableAdapter DBDirect 方法保存数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
本演练提供了有关使用 TableAdapter 的 DBDirect 方法直接对数据库运行 SQL 语句的详细的说明。 TableAdapter 的 DBDirect 方法提供精细的控制对数据库更新级别。 可用于运行特定的 SQL 语句和存储的过程的调用单个`Insert`， `Update`，并`Delete`方法，根据需要由你的应用程序 (而不是重载`Update`执行更新的方法INSERT 和 DELETE 语句都在一个调用中的)。  
  
 在本演练中，你将学会如何执行以下任务：  
  
-   创建一个新**Windows 应用程序**。  
  
-   创建和配置具有的数据集[数据源配置向导](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)。  
  
-   选择要拖动项时要创建窗体上的控件**数据源**窗口。 有关详细信息，请参阅[设置从数据源窗口中拖动时创建的控件](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)。  
  
-   通过将项从创建数据绑定窗体**数据源**拖到窗体的窗口。  
  
-   添加方法，以直接访问数据库并执行插入、 更新和删除...  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你将需要：  
  
-   能够访问 Northwind 示例数据库。 有关详细信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
## <a name="create-a-windows-application"></a>创建 Windows 应用程序  
 第一步是创建**Windows 应用程序**。  
  
#### <a name="to-create-the-new-windows-project"></a>创建新的 Windows 项目  
  
1.  在 Visual Studio 中，在**文件**菜单中，创建一个新**项目**。  
  
2.  将项目命名**TableAdapterDbDirectMethodsWalkthrough**。  
  
3.  选择**Windows 应用程序**，并选择下列**确定**。 有关详细信息，请参阅[客户端应用程序](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)。  
  
     **TableAdapterDbDirectMethodsWalkthrough**创建项目并将其添加到**解决方案资源管理器**。  
  
## <a name="create-a-data-source-from-your-database"></a>从您的数据库创建数据源  
 此步骤中使用**数据源配置向导**创建数据源基于`Region`Northwind 示例数据库中的表。 你必须具有对 Northwind 示例数据库的访问权限，才能创建连接。 有关设置 Northwind 示例数据库的信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
#### <a name="to-create-the-data-source"></a>创建数据源  
  
1.  上**数据**菜单中，选择**显示数据源**。  
  
2.  在中**数据源**窗口中，选择**添加新数据源**以启动**数据源配置向导**。  
  
3.  上**选择数据源类型**屏幕上，选择**数据库**，然后选择**下一步**。  
  
4.  上**选择您的数据连接**屏幕上，执行下列操作之一：  
  
    -   如果下拉列表中包含到 Northwind 示例数据库的数据连接，请选择该连接。  
  
         或  
  
    -   选择**新的连接**以启动**添加/修改连接**对话框。  
  
5.  如果你的数据库需要密码，选择选项以包括敏感数据，然后选择**下一步**。  
  
6.  上**将连接字符串保存到应用程序配置文件**屏幕上，选择**下一步**。  
  
7.  上**选择数据库对象**屏幕上，展开**表**节点。  
  
8.  选择`Region`表，，然后选择**完成**。  
  
     **NorthwindDataSet**添加到项目并`Region`表中将出现**数据源**窗口。  
  
## <a name="addcontrols-to-the-form-to-display-the-data"></a>向窗体的 Addcontrols 以显示数据  
 通过将项从创建数据绑定控件**数据源**窗口拖到窗体上的。  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>若要创建数据绑定 Windows 窗体控件  
  
-   将主**地区**从节点**数据源**拖到窗体的窗口。  
  
     用于导航记录的 <xref:System.Windows.Forms.DataGridView> 控件和工具栏（<xref:System.Windows.Forms.BindingNavigator>）将显示在窗体上。 一个[NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)， [RegionTableAdapter](../data-tools/tableadapter-overview.md)， <xref:System.Windows.Forms.BindingSource>，并<xref:System.Windows.Forms.BindingNavigator>组件栏中出现。  
  
#### <a name="to-add-buttons-that-will-call-the-individual-tableadapter-dbdirect-methods"></a>添加将调用单个 TableAdapter DbDirect 方法的按钮  
  
1.  将三个<xref:System.Windows.Forms.Button>控件从**工具箱**拖动到**Form1** (下面**RegionDataGridView**)。  
  
2.  设置以下**名称**并**文本**上每个按钮的属性。  
  
    |name|Text|  
    |----------|----------|  
    |`InsertButton`|**插入**|  
    |`UpdateButton`|**更新**|  
    |`DeleteButton`|**删除**|  
  
#### <a name="to-add-code-to-insert-new-records-into-the-database"></a>添加将新记录插入数据库所使用的代码  
  
1.  选择**InsertButton**以创建 click 事件的事件处理程序并在代码编辑器中打开你的窗体。  
  
2.  用下面的代码替换 `InsertButton_Click` 事件处理程序：  
  
     [!code-csharp[VbRaddataSaving#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#1)]
     [!code-vb[VbRaddataSaving#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#1)]  
  
#### <a name="to-add-code-to-update-records-in-the-database"></a>添加更新数据库中的记录所使用的代码  
  
1.  双击**UpdateButton**以创建 click 事件的事件处理程序并在代码编辑器中打开你的窗体。  
  
2.  用下面的代码替换 `UpdateButton_Click` 事件处理程序：  
  
     [!code-csharp[VbRaddataSaving#2](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#2)]
     [!code-vb[VbRaddataSaving#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#2)]  
  
#### <a name="to-add-code-to-delete-records-from-the-database"></a>添加代码以从数据库中删除记录  
  
1.  选择**DeleteButton**以创建 click 事件的事件处理程序并在代码编辑器中打开你的窗体。  
  
2.  用下面的代码替换 `DeleteButton_Click` 事件处理程序：  
  
     [!code-csharp[VbRaddataSaving#3](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form1.cs#3)]
     [!code-vb[VbRaddataSaving#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form1.vb#3)]  
  
## <a name="run-the-application"></a>运行此应用程序  
  
#### <a name="to-run-the-application"></a>要运行应用程序  
  
-   选择**F5**运行该应用程序。  
  
-   选择**插入**按钮，并验证新的记录显示在网格中。  
  
-   选择**更新**按钮，然后验证是否在网格中更新记录。  
  
-   选择**删除**按钮，并验证记录是否从网格中被删除。  
  
## <a name="next-steps"></a>后续步骤  
 具体取决于应用程序的要求，有可能想要创建数据绑定窗体后执行的几个步骤。 你可以通过以下操作来增强此演练的效果：  
  
-   将搜索功能添加到该窗体。 有关详细信息，请参阅[如何： 向 Windows 窗体应用程序中添加参数化查询](http://msdn.microsoft.com/library/13db4ad3-56b9-4a0b-b3a5-6a4ff84d4416)。  
  
-   通过选择将其他表添加到数据集**使用向导配置数据集**内**数据源**窗口。 可以通过将相关节点拖到窗体上来添加显示相关数据的控件。 有关详细信息，请参阅[如何：在 Windows 窗体应用程序中显示相关数据](../data-tools/how-to-display-related-data-in-a-windows-forms-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [将数据保存回数据库](../data-tools/save-data-back-to-the-database.md)

