---
title: 数据类继承 （O-R 设计器）
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: af32653c-f4e6-4217-8c5a-e32b322b4918
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 6c6b17ad38e9aae78975e43797931a326955712d
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756732"
---
# <a name="data-class-inheritance-or-designer"></a>数据类继承 （O/R 设计器）

类似于其他对象，LINQ to SQL 类可以使用继承，并从其他类派生。 在代码中，可以通过声明一个类继承自另一个类来指定对象间的继承关系。 在数据库中，可通过多种方式创建继承关系。 **对象关系设计器**(**O/R 设计器**) 支持通常在关系系统中实现的单表继承概念。

在单表继承中，一个数据库表同时包含基类和派生类的列。 使用关系数据时，一个鉴别器列包含的值确定任意给定的记录属于哪个类。 例如，考虑`Persons`表，该表包含所有员工的公司。 一些人是员工，一些人是经理。 `Persons`表包含一个名为列`Type`的员工的经理和值为 2 的值为 1。 `Type`列是鉴别器列。 在此方案中，可以创建一个员工子类，并具有的记录类中填充`Type`值为 2。

配置继承时实体类中使用[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]，拖动的单个表，其中包含继承数据拖到设计器两次： 一次的继承层次结构中每个类。 将表添加到设计器后，连接它们的继承项从**对象关系设计器**工具箱，然后设置四个继承属性中的**属性**窗口。

## <a name="inheritance-properties"></a>继承属性

下表列出了这些继承属性及其说明：

|属性|描述|
|--------------|-----------------|
|**鉴别器属性**|决定当前记录所属的类的属性，该属性映射到列。|
|**基类鉴别器值**|值 (在指定为的列**鉴别器属性**)，它确定记录所属的基类。|
|**在派生的类鉴别器值**|值 (指定为在属性中**鉴别器属性**)，它确定记录所属的派生类。|
|**继承默认值**|属性中的值指定为时，将填充的类**鉴别器属性**不匹配**基类鉴别器值**或**派生的类鉴别器值**。|

创建一个使用继承并对应于关系数据的对象模型可能有些不易理解。 本主题提供了有关配置继承时所需的基本概念及各个属性的信息。 以下主题提供了更清楚的阐释如何配置与继承**O/R 设计器**。

|主题|描述|
|-----------|-----------------|
|[如何： 通过使用 O/R 设计器配置继承](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)|介绍如何配置使用单表继承的使用的实体类**O/R 设计器**。|
|[演练： 创建 LINQ to SQL 类通过使用单表继承 （O/R 设计器）](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)|提供有关如何配置使用单表继承的使用的实体类的分步说明**O/R 设计器**。|

## <a name="see-also"></a>请参阅

- [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [演练： 创建 LINQ to SQL 类 （O-R 设计器）](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [演练： 创建 LINQ to SQL 类通过使用单表继承 （O/R 设计器）](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)
- [入门](/dotnet/framework/data/adonet/sql/linq/getting-started)