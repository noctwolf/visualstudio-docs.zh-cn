---
title: 如何： 更改 DataContext 方法 （O-R 设计器） 的返回类型
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c5b66bff-6dbb-43c0-bffa-317133ca5b9e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5c67d6dea4c64e858acdab25ecc4a6cede6bf262
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089352"
---
# <a name="how-to-change-the-return-type-of-a-datacontext-method-or-designer"></a>如何： 更改 DataContext 方法 （O/R 设计器） 的返回类型
返回类型<xref:System.Data.Linq.DataContext>（创建基于存储的过程或函数） 的方法不同，具体取决于删除存储的过程或函数中的位置**O/R 设计器**。 如果直接将项放在现有实体类上，则将创建具有该实体类返回类型的 <xref:System.Data.Linq.DataContext> 方法（如果该存储过程或函数返回的数据架构与实体类的形状相匹配）。 如果将项放置到的空白区域上**O/R 设计器**、<xref:System.Data.Linq.DataContext>创建返回自动生成的类型的方法。 在将 <xref:System.Data.Linq.DataContext> 方法添加到方法窗格后可以更改该方法的返回类型。 若要检查或更改的返回类型<xref:System.Data.Linq.DataContext>方法中，选择它，然后单击**返回类型**中的属性**属性**窗口。

> [!NOTE]
>  无法还原<xref:System.Data.Linq.DataContext>方法具有返回类型设置为实体类，以使用返回自动生成的类型**属性**窗口。 若要还原<xref:System.Data.Linq.DataContext>方法以返回自动生成的类型，必须将原始数据库对象拖到拖**O/R 设计器**试。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="to-change-the-return-type-of-a-datacontext-method-from-the-auto-generated-type-to-an-entity-class"></a>将 DataContext 方法的返回类型从自动生成类型更改为实体类

1.  在方法窗格中选择该 <xref:System.Data.Linq.DataContext> 方法。

2.  选择**返回类型**中**属性**窗口，然后选择一个可用的实体类中**返回类型**列表。 如果所需的实体类不是在列表中，将其添加到或中创建该**O/R 设计器**以将其添加到列表。

3.  保存 *.dbml*文件。

## <a name="to-change-the-return-type-of-a-datacontext-method-from-an-entity-class-back-to-the-auto-generated-type"></a>将 DataContext 方法的返回类型从实体类重新更改为自动生成类型

1.  选择<xref:System.Data.Linq.DataContext>中的方法**方法**窗格并将其删除。

2.  将数据库对象从**服务器资源管理器**或**数据库资源管理器**上的空白区域**O/R 设计器**。

3.  保存 *.dbml*文件。

## <a name="see-also"></a>请参阅

- [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [DataContext 方法 （O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)
- [如何： 创建映射到存储的过程和函数 （O/R 设计器） 的 DataContext 方法](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)