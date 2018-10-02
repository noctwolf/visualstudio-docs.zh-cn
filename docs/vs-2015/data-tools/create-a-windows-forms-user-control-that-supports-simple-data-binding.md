---
title: 创建支持简单数据绑定的 Windows 窗体用户控件 |Microsoft Docs
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
- custom controls [Visual Studio], Data Sources Window
- Data Sources Window, controls
ms.assetid: b1488366-6dfb-454e-9751-f42fd3f3ddfb
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a5cb2d1e9d1ea175122381c19fa93c9abc07b2a2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477299"
---
# <a name="create-a-windows-forms-user-control-that-supports-simple-data-binding"></a>创建支持简单数据绑定的 Windows 窗体用户控件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[创建支持简单数据绑定的用户控件](https://docs.microsoft.com/visualstudio/data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding)。  
  
  
在 Windows 应用程序中的窗体上显示数据，可以选择从现有控件**工具箱**，或如果你的应用程序需要标准控件中不可用的功能，可以创作自定义控件。 本演练显示了如何创建实现 <xref:System.ComponentModel.DefaultBindingPropertyAttribute> 的控件。 用于实现 <xref:System.ComponentModel.DefaultBindingPropertyAttribute> 的控件可以包含一个可以绑定到数据的属性。 此类控件类似于 <xref:System.Windows.Forms.TextBox> 或 <xref:System.Windows.Forms.CheckBox>。  
  
 控件创作的详细信息，请参阅[在设计时开发 Windows 窗体控件](http://msdn.microsoft.com/library/e5a8e088-7ec8-4fd9-bcb3-9078fd134829)。  
  
 在创作时用于在数据绑定方案中的控件，应实现以下数据绑定特性之一：  
  
|数据绑定特性用法|  
|-----------------------------------|  
|在简单控件上实现 <xref:System.ComponentModel.DefaultBindingPropertyAttribute>（如 <xref:System.Windows.Forms.TextBox>），此类控件用于显示数据的单个列（或属性）。 （本演练页面描述了此过程）。|  
|在控件上实现 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>（如 <xref:System.Windows.Forms.DataGridView>），此类控件用于显示数据列表（或表）。 有关详细信息，请参阅[创建支持复杂数据绑定的 Windows 窗体用户控件](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)。|  
|在控件上实现 <xref:System.ComponentModel.LookupBindingPropertiesAttribute>（如 <xref:System.Windows.Forms.ComboBox>），此类控件用于显示数据列表（或表），也需要显示数据的单个列或属性。 有关详细信息，请参阅[创建支持查找数据绑定的 Windows 窗体用户控件](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)。|  
  
 本演练创建了一个简单控件，用于显示表中单个列的数据。 此示例使用 Northwind 示例数据库的 `Phone` 表中的 `Customers` 列。 简单的用户控件将使用标准的电话号码格式，显示客户的电话号码<xref:System.Windows.Forms.MaskedTextBox>并将掩码设置为电话号码。  
  
 在本演练中，你将学会如何执行以下任务：  
  
-   创建一个新**Windows 应用程序**。  
  
-   添加一个新**用户控件**到你的项目。  
  
-   以可视方式设计用户控件。  
  
-   实现 `DefaultBindingProperty` 特性。  
  
-   创建具有的数据集**数据源配置**向导。  
  
-   设置**Phone**中的列**数据源**窗口以使用新的控件。  
  
-   创建一个用于在新控件中显示数据的窗体。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你将需要：  
  
-   能够访问 Northwind 示例数据库。 有关详细信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
## <a name="create-a-windows-application"></a>创建 Windows 应用程序  
 第一步是创建**Windows 应用程序**。  
  
#### <a name="to-create-the-new-windows-project"></a>创建新的 Windows 项目  
  
1.  在 Visual Studio 中，从**文件**菜单中，创建一个新**项目**。  
  
2.  将项目命名**SimpleControlWalkthrough**。  
  
3.  选择**Windows 应用程序**然后单击**确定**。 有关详细信息，请参阅[客户端应用程序](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)。  
  
     **SimpleControlWalkthrough**项目时创建，并添加到**解决方案资源管理器**。  
  
## <a name="add-a-user-control-to-the-project"></a>将用户控件添加到项目  
 本演练创建一个简单的可数据绑定控件从**用户控件**，因此，添加**用户控件**项**SimpleControlWalkthrough**项目。  
  
#### <a name="to-add-a-user-control-to-the-project"></a>将用户控件添加到项目中  
  
1.  从**项目**菜单中，选择**添加用户控件**。  
  
2.  类型`PhoneNumberBox`在名称区域中，单击**添加**。  
  
     **PhoneNumberBox**控件添加到**解决方案资源管理器**，并在设计器中打开。  
  
## <a name="design-the-phonenumberbox-control"></a>设计 PhoneNumberBox 控件  
 本演练对现有 <xref:System.Windows.Forms.MaskedTextBox> 进行了扩展，以创建 `PhoneNumberBox` 控件。  
  
#### <a name="to-design-the-phonenumberbox-control"></a>设计 PhoneNumberBox 控件  
  
1.  拖动<xref:System.Windows.Forms.MaskedTextBox>从**工具箱**到用户控件的设计图面。  
  
2.  选择智能标记上<xref:System.Windows.Forms.MaskedTextBox>只需拖放，然后选择**设置掩码**。  
  
3.  选择**电话号码**中**输入掩码**对话框中，然后单击**确定**以设置掩码。  
  
## <a name="add-the-required-data-binding-attribute"></a>添加所需的数据绑定属性  
 对于支持数据绑定的简单控件，应实现 <xref:System.ComponentModel.DefaultBindingPropertyAttribute>。  
  
#### <a name="to-implement-the-defaultbindingproperty-attribute"></a>实现 DefaultBindingProperty 特性  
  
1.  将 `PhoneNumberBox` 控件切换到代码视图。 (在**视图**菜单中，选择**代码**。)  
  
2.  将 `PhoneNumberBox` 中的代码替换为以下内容：  
  
     [!code-csharp[VbRaddataDisplaying#3](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/PhoneNumberBox.cs#3)]
     [!code-vb[VbRaddataDisplaying#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/PhoneNumberBox.vb#3)]  
  
3.  从 **“生成”** 菜单中选择 **“生成解决方案”**。  
  
## <a name="create-a-data-source-from-your-database"></a>从您的数据库创建数据源  
 此步骤中使用**数据源配置**向导创建数据源基于`Customers`Northwind 示例数据库中的表。 你必须具有对 Northwind 示例数据库的访问权限，才能创建连接。 有关设置 Northwind 示例数据库的信息，请参阅[如何： 安装示例数据库](../data-tools/how-to-install-sample-databases.md)。  
  
#### <a name="to-create-the-data-source"></a>创建数据源  
  
1.  在 **“数据”** 菜单上，单击 **“显示数据源”**。  
  
2.  在中**数据源**窗口中，选择**添加新数据源**以启动**数据源配置**向导。  
  
3.  上**选择数据源类型**页上，选择**数据库**，然后单击**下一步**。  
  
4.  上**选择您的数据连接**页上，执行下列操作之一：  
  
    -   如果下拉列表中包含到 Northwind 示例数据库的数据连接，请选择该连接。  
  
    -   选择**新的连接**以启动**添加/修改连接**对话框。  
  
5.  如果你的数据库需要密码，选择选项以包括敏感数据，然后单击**下一步**。  
  
6.  上**将连接字符串保存到应用程序配置文件**页上，单击**下一步**。  
  
7.  上**选择数据库对象**页上，展开**表**节点。  
  
8.  选择`Customers`表，并单击**完成**。  
  
     **NorthwindDataSet**添加到你的项目，并`Customers`表中将出现**数据源**窗口。  
  
## <a name="set-the-phone-column-to-use-the-phonenumberbox-control"></a>设置要使用 phonenumberbox 控件的 phone 列  
 内**数据源**窗口中，可以设置要在项拖动到窗体之前创建的控件。  
  
#### <a name="to-set-the-phone-column-to-bind-to-the-phonenumberbox-control"></a>将“电话”列设置为绑定到“PhoneNumberBox”控件  
  
1.  打开**Form1**在设计器中。  
  
2.  展开**客户**中的节点**数据源**窗口。  
  
3.  单击下拉箭头**客户**节点，然后选择**详细信息**从控件列表。  
  
4.  单击下拉箭头**Phone**列中，选择**自定义**。  
  
5.  选择**PhoneNumberBox**从列表中**关联的控件**中**数据 UI 自定义选项**对话框。  
  
6.  单击下拉箭头**Phone**列中，选择**PhoneNumberBox**。  
  
## <a name="addcontrols-to-the-form"></a>向窗体 Addcontrols  
 可以通过将项从创建数据绑定控件**数据源**拖到窗体的窗口。  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>在窗体上创建数据绑定控件  
  
-   将主**客户**从节点**数据源**窗口中的拖到窗体，并验证`PhoneNumberBox`控件用于显示中的数据`Phone`列。  
  
     带有描述性标签的数据绑定控件将显示在窗体上，同时还显示一个工具条 (<xref:System.Windows.Forms.BindingNavigator>)，用于在记录间进行导航。 一个[NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)， [CustomersTableAdapter](../data-tools/tableadapter-overview.md)， <xref:System.Windows.Forms.BindingSource>，并<xref:System.Windows.Forms.BindingNavigator>组件栏中出现。  
  
## <a name="run-the-application"></a>运行此应用程序  
  
#### <a name="to-run-the-application"></a>要运行应用程序  
  
-   按 F5 运行该应用程序。  
  
## <a name="next-steps"></a>后续步骤  
 根据应用程序的需求，在创建了支持数据绑定的控件后，可能还需要执行一些步骤。 接下来的一些常见步骤包括：  
  
-   将你的自定义控件置于控件库中，以便在其他应用程序中重用它们。  
  
-   创建支持更复杂的数据绑定方案的控件。 有关详细信息，请参阅[创建支持复杂数据绑定的 Windows 窗体用户控件](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)并[创建支持查找数据绑定的 Windows 窗体用户控件](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [设置从“数据源”窗口中拖动时要创建的控件](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)

