---
title: 如何： 创建映射到存储的过程和函数 （O-R 设计器） 的 DataContext 方法
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 53829ffaeab44eb758b1850f5619de43db31e589
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089680"
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>如何： 创建映射到存储的过程和函数 （O/R 设计器） 的 DataContext 方法
您可以添加存储的过程和函数**O/R 设计器**作为<xref:System.Data.Linq.DataContext>方法。 调用该方法并传入所需参数将对数据库运行存储过程或函数，并返回 <xref:System.Data.Linq.DataContext> 方法的返回类型的数据。 有关详细信息<xref:System.Data.Linq.DataContext>方法，请参阅[DataContext 方法 （O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)。

> [!NOTE]
>  此外可以使用存储的过程重写默认[!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)]执行插入、 更新和删除操作将更改从实体类保存到数据库时的运行时行为。 有关详细信息，请参阅[如何： 分配存储的过程以便执行更新、 插入和删除操作 （O/R 设计器）](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)。

## <a name="create-datacontext-methods"></a>创建 DataContext 方法
 您可以创建<xref:System.Data.Linq.DataContext>方法通过拖动存储过程或函数从 * * 服务器资源管理器或**数据库资源管理器**拖动到**O/R 设计器**。

> [!NOTE]
>  生成的返回类型<xref:System.Data.Linq.DataContext>方法不同，具体取决于删除存储的过程或函数上的位置**O/R 设计器**。 如果直接将项放在现有实体类上，则将创建具有该实体类返回类型的 <xref:System.Data.Linq.DataContext> 方法。 项放的空白区域**O/R 设计器**创建<xref:System.Data.Linq.DataContext>返回自动生成的类型的方法。 可以更改的返回类型<xref:System.Data.Linq.DataContext>方法之后将其添加到**方法**窗格。 若要检查或更改的返回类型<xref:System.Data.Linq.DataContext>方法中，选择它，并检查**返回类型**中的属性**属性**窗口。 有关详细信息，请参阅[如何： 更改 DataContext 方法 （O/R 设计器） 的返回类型](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>创建返回自动生成类型的 DataContext 方法

1.  在中**服务器资源管理器**或**数据库资源管理器**，展开**Stored Procedures**所使用的数据库的节点。

2.  找到所需的存储的过程并将其拖到空白的区域**O/R 设计器**。

     <xref:System.Data.Linq.DataContext>方法创建具有自动生成的返回类型，并出现在**方法**窗格。

### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>创建具有实体类的返回类型的 DataContext 方法

1.  在中**服务器资源管理器**或**数据库资源管理器**，展开**Stored Procedures**所使用的数据库的节点。

2.  找到所需的存储的过程并将其拖至现有实体类中**O/R 设计器**。

     <xref:System.Data.Linq.DataContext>方法创建具有所选的实体类返回类型，并出现在**方法**窗格。

> [!NOTE]
>  有关更改返回类型的现有<xref:System.Data.Linq.DataContext>方法，请参阅[如何： 更改 DataContext 方法 （O/R 设计器） 的返回类型](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)。

## <a name="see-also"></a>请参阅

- [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [DataContext 方法 （O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)
- [演练： 创建 LINQ to SQL 类](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Visual Basic 中的 LINQ 简介](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)
- [C# 中的 LINQ](/dotnet/csharp/linq/linq-in-csharp)