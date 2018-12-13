---
title: 演练： 在 Windows 窗体上显示相关的数据 |Microsoft Docs
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
- displaying data on forms, walkthroughs
- Windows Forms, displaying data
- data [Visual Studio], displaying on Windows Forms
- master-details lists, displaying on Windows Forms
- data [Visual Studio], master-details
- displaying tables, related data
- displaying table data
- displaying table information
ms.assetid: fc4b9055-2bf3-4028-8aad-9489820d69f6
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 882c8229c105920efe247a54e9525a262e6a3246
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49282667"
---
# <a name="walkthrough-displaying-related-data-on-a-windows-form"></a>演练：在 Windows 窗体上显示相关数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在很多应用程序方案中，你需要使用来自多个表中的数据（通常是相关表中的数据）。 也就是说，你需要使用父子关系。 例如，你会需要创建一个窗体，在该窗体中选择客户记录的同时显示该客户的订单。 通过将子 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 的 <xref:System.Windows.Forms.BindingSource> 属性设置为父 <xref:System.Windows.Forms.BindingSource>（不是子表），并将子 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 的 <xref:System.Windows.Forms.BindingSource> 属性设置为联系父表和子表的数据关系，可在窗体中显示相关记录。  
  
 本演练涉及以下任务：  
  
-   创建**Windows 应用程序**项目。  
  
-   创建和配置应用程序中的数据集基于`Customers`并`Orders`使用 Northwind 数据库中的表[数据源配置向导](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)。  
  
-   添加控件以显示 `Customers` 表中的数据。  
  
-   添加控件以基于所选的 `Orders` 显示 `Customer`。  
  
-   通过选择不同的客户并验证是否能正确显示所选客户的订单来测试应用程序。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你需要：  
  
-   能够访问 Northwind 示例数据库。 若要安装示例数据库，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
## <a name="creating-the-project"></a>创建项目  
 第一步是创建**Windows 应用程序**。  
  
#### <a name="to-create-the-windows-application-project"></a>创建 Windows 应用程序项目  
  
1.  从**文件**菜单中，创建一个新项目。  
  
2.  将项目命名为 `RelatedDataWalkthrough`。  
  
3.  选择**Windows 应用程序**然后单击**确定**。 有关详细信息，请参阅[客户端应用程序](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)。  
  
     **RelatedDataWalkthrough**创建项目并将其添加到**解决方案资源管理器**。  
  
## <a name="creating-the-data-source"></a>创建数据源  
 此步骤根据 Northwind 示例数据库中的 `Customers` 表和 `Orders` 表创建一个数据集。  
  
#### <a name="to-create-the-data-source"></a>创建数据源  
  
1.  在 **“数据”** 菜单上，单击 **“显示数据源”**。  
  
2.  在中**数据源**窗口中，选择**添加新数据源**以启动**数据源配置向导**。  
  
3.  在 **“选择数据源类型”** 页上选择 **“数据库”** ，然后单击 **“下一步”**。  
  
4.  上**选择您的数据连接**页面上执行以下项之一：  
  
    -   如果下拉列表中包含到 Northwind 示例数据库的数据连接，请选择该连接。  
  
         或  
  
    -   选择**新的连接**以启动**添加/修改连接**对话框。  
  
5.  如果你的数据库需要密码，选择选项以包括敏感数据，然后单击**下一步**。  
  
6.  单击**下一步**上**将连接字符串保存到应用程序配置文件**页。  
  
7.  展开**表**上的节点**选择数据库对象**页。  
  
8.  选择**客户**并**订单**表，并单击**完成**。  
  
     **NorthwindDataSet**添加到项目并**客户**表中将显示**数据源**窗口。  
  
## <a name="creating-controls-to-display-data-from-the-customers-table"></a>创建控件以显示 Customers 表中的数据  
  
#### <a name="to-create-controls-to-display-the-customer-data-parent-records"></a>创建控件以显示客户数据（父记录）  
  
1.  在中**数据源**窗口中，选择**客户**表，并单击下拉箭头。  
  
2.  选择**详细信息**菜单中。  
  
3.  将主**客户**从节点**数据源**窗口拖到顶部**Form1**。  
  
     带有描述性标签的数据绑定控件将显示在窗体上，同时还显示一个工具条 (<xref:System.Windows.Forms.BindingNavigator>)，用于在记录间进行导航。 一个[NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)， [CustomersTableAdapter](../data-tools/tableadapter-overview.md)， <xref:System.Windows.Forms.BindingSource>，并<xref:System.Windows.Forms.BindingNavigator>组件栏中出现。  
  
## <a name="creating-controls-to-display-data-from-the-orders-table"></a>创建控件以显示 Orders 表中的数据  
 ![显示关系数据源窗口](../data-tools/media/datasources2.gif "DataSources2")  
  
#### <a name="to-create-controls-to-display-the-orders-for-each-customer-child-records"></a>创建控件以显示每个客户的订单（子记录）  
  
-   在中**数据源**窗口中，展开**客户**节点，然后选择中的最后一列**客户**表中，这是可展开**订单**节点，并将它拖到底部**Form1**。  
  
     <xref:System.Windows.Forms.DataGridView> 被添加到窗体，且新的 <xref:System.Windows.Forms.BindingSource> (`OrdersBindingSource`) 和 TableAdapter (`OrdersTableAdapter`) 添加到组件栏。  
  
    > [!NOTE]
    >  打开[属性窗口](../ide/reference/properties-window.md)，然后选择**ordersbindingsource**。 检查 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 和 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 属性以查看配置绑定以显示相关记录的方式。 将 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 设置为 `CustomersBindingSource`（父表的 <xref:System.Windows.Forms.BindingSource>），而不是 `Orders` 表。 将 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 属性设置为 `FK_Orders_Customers`（它是使表联系在一起的 <xref:System.Data.DataRelation> 对象的名称）。  
  
## <a name="testing-the-application"></a>测试应用程序  
  
#### <a name="to-test-the-application"></a>测试应用程序  
  
1.  按 F5 运行该应用程序。  
  
2.  选择使用不同的客户**CustomersBindingNavigator**若要验证正确的订单将显示在<xref:System.Windows.Forms.DataGridView>。  
  
## <a name="next-steps"></a>后续步骤  
 根据应用程序的需求，在创建了主/详细信息窗体后，还需要执行一些步骤。 可对本演练所进行的一项增强是：  
  
-   通过将参数化添加到 `Customers` 表来对 `Customers` 记录进行筛选。 若要执行此操作，请选择显示来自数据的任何控件`Customers`表中，单击智能标记，并选择**添加查询**。 完成[搜索条件生成器对话框](http://msdn.microsoft.com/library/0b306b92-f35e-45ef-a4be-3f653cd00c3d)。 有关详细信息，请参阅[如何： 向 Windows 窗体应用程序中添加参数化查询](http://msdn.microsoft.com/library/13db4ad3-56b9-4a0b-b3a5-6a4ff84d4416)。  
  
## <a name="see-also"></a>请参阅  
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [“数据源”窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [添加新数据源](../data-tools/add-new-data-sources.md)   
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)   
 [如何： 在 Windows 中的数据窗体应用程序中显示相关](../data-tools/how-to-display-related-data-in-a-windows-forms-application.md)   
 [BindingSource 组件概述](http://msdn.microsoft.com/library/be838caf-fcb0-4b68-827f-58b2c04b747f)   
 [BBindingNavigator 控件概述](http://msdn.microsoft.com/library/4423eede-f8d1-4d02-822f-5bf8432680d0)