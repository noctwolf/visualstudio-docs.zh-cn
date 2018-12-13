---
title: 将数据绑定的自定义对象
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], object binding
- data [Visual Studio], binding to objects
- object binding
- binding, to objects
ms.assetid: ed743ce6-73af-45e5-a8ff-045eddaccc86
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: b7790f5205aa24a68505a1b34e97283aff05e13c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49950130"
---
# <a name="bind-objects-as-data-sources-in-visual-studio"></a>将对象绑定作为 Visual Studio 中的数据源

Visual Studio 提供用于为你的应用程序中的数据源使用自定义对象的设计时工具。 当你想要将绑定到 UI 控件的对象中存储数据库中的数据时，建议的方法是使用实体框架生成的类。 Entity Framework 自动生成所有样板更改跟踪代码，这意味着，对本地对象的任何更改时，会自动保留到数据库 DbSet 对象上调用 AcceptChanges。 有关详细信息，请参阅[Entity Framework 文档](https://ef.readthedocs.org/en/latest/)。

> [!TIP]
> 如果你的应用程序已基于数据集，才应考虑到这篇文章中的对象绑定的方法。 如果你已熟悉的数据集，并进行处理的数据是表格和不太复杂或过大，还可以使用这些方法。 更简单的示例，涉及将数据加载到对象直接，通过使用 DataReader 并手动更新用户界面而无需进行数据绑定，请参阅[使用 ADO.NET 创建简单的数据应用](../data-tools/create-a-simple-data-application-by-using-adonet.md)。

## <a name="object-requirements"></a>对象要求

若要处理的数据设计工具在 Visual Studio 中的自定义对象的唯一要求是，对象所需的至少一个公共属性。

通常情况下，自定义对象不需要任何特定的接口，构造函数或要充当应用程序的数据源属性。 但是，如果你想要将对象从**数据源**窗口到设计图面来创建数据绑定控件，并且如果该对象实现<xref:System.ComponentModel.ITypedList>或<xref:System.ComponentModel.IListSource>接口，该对象必须具有默认值构造函数。 否则为 Visual Studio 无法实例化的数据源对象，并将项拖至设计图面上时显示错误。

## <a name="examples-of-using-custom-objects-as-data-sources"></a>作为数据源使用自定义对象的示例

虽然有无数的使用方法来实现应用程序逻辑，使用对象作为数据源时，SQL 的情况下存在数据库是可以通过使用 Visual Studio 生成的 TableAdapter 对象来简化的几个标准操作。 此页说明如何实现使用 Tableadapter 这些标准过程。 它不是用于创建自定义对象应作为指南。 例如，你通常将执行以下的标准操作而不考虑特定实现的对象或应用程序的逻辑：

-   将数据加载到对象 （通常是从数据库）。

-   创建类型化的对象的集合。

-   将对象添加到和从集合中删除对象。

-   向窗体上的用户显示的对象数据。

-   更改并正在编辑的对象中的数据。

-   将数据从对象保存到数据库。

### <a name="load-data-into-objects"></a>将数据加载到对象

对于此示例中，您将数据加载到您的对象使用 Tableadapter。 默认情况下，使用两种类型的方法，从数据库提取数据并填充数据的表创建 Tableadapter。

-   `TableAdapter.Fill`方法返回的数据填充现有数据表。

-   `TableAdapter.GetData`方法返回一个新的数据集填充数据。

加载数据使用自定义对象的最简单方法是调用`TableAdapter.GetData`方法中，循环遍历返回的数据表中的行的集合，并填充每个行中的值与每个对象。 您可以创建`GetData`返回填充的数据表的任何添加到 TableAdapter 的查询的方法。

> [!NOTE]
> Visual Studio 名称 TableAdapter 查询`Fill`和`GetData`默认情况下，但可以将这些名称更改为任何有效的方法名称。

下面的示例演示如何循环访问在数据表中的行和填充数据的对象：

[!code-csharp[VbRaddataConnecting#4](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_1.cs)]
[!code-vb[VbRaddataConnecting#4](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_1.vb)]

### <a name="create-a-typed-collection-of-objects"></a>创建类型化的对象的集合

可以为您的对象，创建集合类，也可以使用自动提供的类型化的集合[BindingSource 组件](/dotnet/framework/winforms/controls/bindingsource-component)。

当要创建的自定义集合类的对象时，我们建议从继承<xref:System.ComponentModel.BindingList%601>。 此泛型类提供功能来管理你的集合，以及能够引发事件通知发送到 Windows 窗体中的数据绑定基础结构。

中的自动生成的集合<xref:System.Windows.Forms.BindingSource>使用<xref:System.ComponentModel.BindingList%601>其类型的集合。 如果你的应用程序不需要其他功能，可以维护你的集合内<xref:System.Windows.Forms.BindingSource>。 有关详细信息，请参阅<xref:System.Windows.Forms.BindingSource.List%2A>属性的<xref:System.Windows.Forms.BindingSource>类。

> [!NOTE]
> 如果你的集合要求没有提供的基实现的功能<xref:System.ComponentModel.BindingList%601>，应创建自定义集合，以便您可以根据需要添加到类。

下面的代码演示如何创建强类型化的集合类`Order`对象：

[!code-csharp[VbRaddataConnecting#8](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_2.cs)]
[!code-vb[VbRaddataConnecting#8](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_2.vb)]

### <a name="add-objects-to-a-collection"></a>将对象添加到集合

通过调用的对象添加到集合`Add`方法的自定义集合类或的<xref:System.Windows.Forms.BindingSource>。

> [!NOTE]
> `Add`方法会自动提供为自定义集合时从继承<xref:System.ComponentModel.BindingList%601>。

下面的代码演示如何将对象添加到中的类型化集合<xref:System.Windows.Forms.BindingSource>:

[!code-csharp[VbRaddataConnecting#5](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_3.cs)]
[!code-vb[VbRaddataConnecting#5](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_3.vb)]

 下面的代码演示如何将对象添加到继承的类型集合<xref:System.ComponentModel.BindingList%601>:

> [!NOTE]
> 在此示例中，`Orders`集合是的一个属性`Customer`对象。

[!code-csharp[VbRaddataConnecting#6](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_4.cs)]
[!code-vb[VbRaddataConnecting#6](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_4.vb)]

### <a name="remove-objects-from-a-collection"></a>从集合中删除对象

您从集合中移除对象通过调用`Remove`或`RemoveAt`方法的自定义集合类或的<xref:System.Windows.Forms.BindingSource>。

> [!NOTE]
> `Remove`并`RemoveAt`方法自动提供为自定义集合，当从继承<xref:System.ComponentModel.BindingList%601>。

下面的代码演示如何查找并删除对象中的类型化集合<xref:System.Windows.Forms.BindingSource>与<xref:System.Windows.Forms.BindingSource.RemoveAt%2A>方法：

[!code-csharp[VbRaddataConnecting#7](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_5.cs)]
[!code-vb[VbRaddataConnecting#7](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_5.vb)]

### <a name="display-object-data-to-users"></a>向用户显示对象数据

若要显示给用户的对象中的数据，创建对象数据源使用**数据源配置**向导，然后将整个对象或单独的属性拖动到窗体从**数据源**窗口。

### <a name="modify-the-data-in-objects"></a>修改对象中的数据

若要编辑自定义对象绑定到 Windows 窗体控件中的数据，只需编辑数据绑定控件中 （或直接在对象的属性中）。 数据绑定体系结构更新的对象中的数据。

如果应用程序需要的更改跟踪和回滚建议的更改到其原始值，则必须在您的对象模型中实现此功能。 有关如何保留跟踪数据的表的建议的更改示例，请参阅<xref:System.Data.DataRowState>， <xref:System.Data.DataSet.HasChanges%2A>，和<xref:System.Data.DataTable.GetChanges%2A>。

### <a name="save-data-in-objects-back-to-the-database"></a>将数据保存回数据库的对象中

通过将值从您的对象传递到 TableAdapter 的 DBDirect 方法将数据保存回数据库。

Visual Studio 创建可以直接对数据库执行的 DBDirect 方法。 这些方法不需要 DataSet 或 DataTable 对象。

|TableAdapter DBDirect 方法|描述|
| - |-----------------|
|`TableAdapter.Insert`|将新记录添加到数据库，您可以在各列的值作为方法参数中传递。|
|`TableAdapter.Update`|更新现有数据库中的记录。 Update 方法使用原始的和新列的值作为方法参数。 用于查找的原始记录的原始值和新值用于更新该记录。<br /><br /> `TableAdapter.Update`方法还可用于将数据集的更改回数据库中，通过采用<xref:System.Data.DataSet>， <xref:System.Data.DataTable>， <xref:System.Data.DataRow>，或数组<xref:System.Data.DataRow>的方法参数。|
|`TableAdapter.Delete`|删除现有的基于原始列值作为方法参数传入数据库中的记录。|

若要保存数据的对象的集合，请依次通过 （例如，使用的下一步循环） 的对象的集合。 使用 TableAdapter 的 DBDirect 方法将为每个对象的值发送到数据库。

下面的示例演示如何使用`TableAdapter.Insert`DBDirect 方法来添加新客户直接到数据库：

[!code-csharp[VbRaddataSaving#23](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_6.cs)]
[!code-vb[VbRaddataSaving#23](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_6.vb)]

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)