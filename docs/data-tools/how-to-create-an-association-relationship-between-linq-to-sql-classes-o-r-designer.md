---
title: 如何创建 LINQ to SQL 类使用 O/R 设计器之间的关系
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 56133e65-81f3-44c3-bc28-ffdd0671a0d2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 9d7bf1be05ebabcaac319cce591cf82cd2ab5f5d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60112281"
---
# <a name="how-to-create-an-association-between-linq-to-sql-classes-or-designer"></a>如何：创建 LINQ to SQL 类 （O/R 设计器） 之间的关联
[!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 中实体类之间的关联类似于数据库中表之间的关系。 可以使用“关联编辑器”对话框创建实体类之间的关联。

使用“关联编辑器”对话框创建关联时，必须选择父类和子类。 父类是包含主键的实体类；子类是包含外键的实体类。 例如，如果已创建实体类映射到`Northwind Customers`并`Orders`表，`Customer`类将是父类和`Order`类将是子类。

> [!NOTE]
>  当您将从表**服务器资源管理器**或**数据库资源管理器**拖到**对象关系设计器**(**O/R 设计器**)，将自动创建基于数据库中的现有外键关系的关联。

## <a name="association-properties"></a>关联属性
创建关联后，在 O/R 设计器中选择该关联时，“属性”窗口中将有一些可配置属性。 （关联是用相关类之间的连线表示的。）下表提供对关联的属性的说明。

|属性|描述|
|--------------|-----------------|
|**基数**|控制关联是一对多关系还是一对一关系。|
|**子属性**|指定是否在父类上创建一个属性，作为关联关系外键一方上的子记录的集合或对这些子记录的引用。 例如，在之间的关联`Customer`并`Order`，则**子属性**设置为**True**，一个名为属性`Orders`的父类上创建。|
|**父属性**|子类上引用关联父类的属性。 例如，在之间的关联`Customer`并`Order`，一个名为属性`Customer`引用关联的客户订单上创建对`Order`类。|
|**参与的属性**|显示关联属性，并提供一个省略号按钮 (...)，该按钮可重新打开“关联编辑器”对话框。|
|**唯一**|指定外目标列是否具有唯一性约束。|

## <a name="to-create-an-association-between-entity-classes"></a>创建实体类之间的关联

1. 右击表示关联中的父类的实体类，指向“添加”，然后单击“关联”。

2. 验证在“关联编辑器”对话框中是否选择了正确的“父类”。

3. 选择组合框中的“子类”。

4. 选择实现类之间的关联的“关联属性”。 通常，这种关联对应于数据库中定义的外键关系。 例如，在`Customers`并`Orders`关联，**关联属性**是`CustomerID`为每个类。

5. 单击“确定”创建关联。

## <a name="see-also"></a>请参阅

- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [演练：创建 LINQ to SQL 类](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [DataContext 方法（O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)
- [如何：表示主键](/dotnet/framework/data/adonet/sql/linq/how-to-represent-primary-keys)