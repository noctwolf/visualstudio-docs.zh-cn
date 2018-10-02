---
title: 演练： 在 Windows 窗体上显示数据 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
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
- displaying data on forms, walkthroughs
- Windows Forms, displaying data
- Windows applications, displaying data
- data binding, Windows Forms
- data [Visual Studio], displaying on Windows Forms
- forms, displaying data
ms.assetid: f6e08c2c-c792-43de-adf3-3e52c0100225
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 3decf0da6dd6d16c0128fdaeedf2fcd0cea94871
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481248"
---
# <a name="walkthrough-displaying-data-on-a-windows-form"></a>演练：在 Windows 窗体上显示数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在应用程序开发中最常用的方案之一是在基于 Windows 的应用程序中的窗体上显示数据。 可以在窗体上显示数据，通过将项从[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)拖到窗体。 本演练将创建一个简单窗体，用于在几个单独的控件中显示单个表的数据。 本示例使用源自 Northwind 示例数据库的 `Customers` 表。  
  
 本演练涉及以下任务：  
  
-   创建一个新**Windows 应用程序**项目。  
  
-   创建和配置具有的数据集[数据源配置向导](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)。  
  
-   选择要拖动项时要创建窗体上的控件**数据源**窗口。 有关详细信息，请参阅[设置从数据源窗口中拖动时创建的控件](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)。  
  
-   通过将项从创建数据绑定控件**数据源**窗口拖到窗体上的。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你需要：  
  
-   能够访问 Northwind 示例数据库。 有关详细信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
## <a name="creating-the-windows-application"></a>创建 Windows 应用程序  
 第一步是创建**Windows 应用程序**项目。  
  
#### <a name="to-create-the-new-windows-application-project"></a>创建新的 Windows 应用程序项目  
  
1.  从**文件**菜单中，创建一个新项目。  
  
2.  将项目命名为 `DisplayingDataonaWindowsForm`。  
  
3.  选择**Windows 应用程序**然后单击**确定**。 有关详细信息，请参阅[客户端应用程序](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)。  
  
     **DisplayingDataonaWindowsForm**创建项目并将其添加到**解决方案资源管理器**。  
  
## <a name="creating-the-data-source"></a>创建数据源  
 此步骤中创建一个数据源使用**数据源配置向导**基于`Customers`Northwind 示例数据库中的表。 你必须具有对 Northwind 示例数据库的访问权限，才能创建连接。 有关设置 Northwind 示例数据库的信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
#### <a name="to-create-the-data-source"></a>创建数据源  
  
1.  在 **“数据”** 菜单上，单击 **“显示数据源”**。  
  
2.  在中**数据源**窗口中，选择**添加新数据源**以启动**数据源配置向导**。  
  
3.  在 **“选择数据源类型”** 页上选择 **“数据库”** ，然后单击 **“下一步”**。  
  
4.  上**选择您的数据连接**页面上执行以下项之一：  
  
    -   如果下拉列表中包含到 Northwind 示例数据库的数据连接，请选择该连接。  
  
         或  
  
    -   选择**新的连接**以启动**添加/修改连接**对话框...  
  
5.  如果你的数据库需要密码，选择选项以包括敏感数据，然后单击**下一步**。  
  
6.  单击**下一步**上**将连接字符串保存到应用程序配置文件**页。  
  
7.  展开**表**上的节点**选择数据库对象**页。  
  
8.  选择**客户**表，并单击**完成**。  
  
     **NorthwindDataSet**添加到项目并**客户**表中将显示**数据源**窗口。  
  
## <a name="setting-the-controls-to-be-created"></a>设置要创建的控件  
 在本演练中的数据将在**详细信息**，数据显示在单独控件中的布局。 (另一种方法是默认值**网格**布局，其中的数据显示在<xref:System.Windows.Forms.DataGridView>控件。)  
  
#### <a name="to-set-the-drop-type-for-the-items-in-the-data-sources-window"></a>设置“数据源”窗口中项的拖放类型  
  
1.  展开**客户**中的节点**数据源**窗口。  
  
2.  拖放类型更改**客户**表向**详细信息**通过选择**详细信息**上的下拉列表从**客户**节点。 有关详细信息，请参阅[设置从数据源窗口中拖动时创建的控件](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)。  
  
3.  更改**CustomerID**通过选择为标签列的拖放类型**标签**从控件列表上**CustomerID**节点。  
  
## <a name="creating-the-form"></a>创建窗体  
 通过将项从创建数据绑定控件**数据源**窗口拖到窗体上的。  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>在窗体上创建数据绑定控件  
  
-   将主**客户**从节点**数据源**拖到窗体的窗口。  
  
     带有描述性标签的数据绑定控件将显示在窗体上，同时还显示一个工具条 (<xref:System.Windows.Forms.BindingNavigator>)，用于在记录间进行导航。 一个[NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)， [CustomersTableAdapter](../data-tools/tableadapter-overview.md)， <xref:System.Windows.Forms.BindingSource>，并<xref:System.Windows.Forms.BindingNavigator>组件栏中出现。  
  
## <a name="testing-the-application"></a>测试应用程序  
  
#### <a name="to-run-the-application"></a>运行应用程序  
  
-   按 F5。  
  
-   使用 <xref:System.Windows.Forms.BindingNavigator> 控件导航记录。  
  
## <a name="next-steps"></a>后续步骤  
 根据应用程序的需求，在创建了绑定数据的 Windows 窗体后，还需要执行一些步骤。 你可以通过以下操作来增强此演练的效果：  
  
-   将搜索功能添加到该窗体。 有关详细信息，请参阅[如何： 向 Windows 窗体应用程序中添加参数化查询](http://msdn.microsoft.com/library/13db4ad3-56b9-4a0b-b3a5-6a4ff84d4416)。  
  
-   添加将更新发送回数据库的功能。 有关详细信息，请参阅[演练： 将数据保存到数据库 （单个表）](http://msdn.microsoft.com/library/68befa96-7463-43e8-abcf-dc2f42ccd53d)。  
  
-   添加`Orders`通过选择数据集的表**使用向导配置数据集**内**数据源**窗口。 然后，可以添加显示相关的数据的控件**订单**节点 (下面**传真**中的列**客户**表) 拖到窗体。 有关详细信息，请参阅[如何：在 Windows 窗体应用程序中显示相关数据](../data-tools/how-to-display-related-data-in-a-windows-forms-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [添加新数据源](../data-tools/add-new-data-sources.md)   
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)