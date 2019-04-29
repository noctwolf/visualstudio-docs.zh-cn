---
title: 使用 TableAdapter 更新数据
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], saving
- data [Visual Studio], TableAdapters
- updating data, TableAdapters
- TableAdapters, updating data
- data [Visual Studio], updating
- saving data
ms.assetid: 5e32e10e-9bac-4969-9bdd-b8f6919d3516
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: ca5161d0ddb73a72b88f36e85bda9206839aec3d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62565855"
---
# <a name="update-data-by-using-a-tableadapter"></a>使用 TableAdapter 更新数据

在数据集中的数据已修改并验证后，您可以发送更新后的数据返回到数据库通过调用`Update`方法[TableAdapter](../data-tools/create-and-configure-tableadapters.md)。 `Update`方法更新单个数据表，并运行基于的正确命令 （INSERT、 UPDATE 或 DELETE）<xref:System.Data.DataRow.RowState%2A>的表中每个数据行。 时数据集具有相关表，Visual Studio 生成一个 TableAdapterManager 类，用于执行更新操作。 TableAdapterManager 类可确保按正确的顺序基于数据库中定义的外键约束进行更新。 当您使用数据绑定控件时，数据绑定体系结构将创建调用 tableAdapterManager TableAdapterManager 类的一个成员变量。

> [!NOTE]
> 当您尝试使用数据集的内容更新数据源时，你会遇到错误。 若要避免错误，我们建议您将调用该适配器的代码`Update`方法内的`try` / `catch`块。

 更新数据源的确切步骤可以根据业务需求而有所不同，但包括以下步骤：

1. 调用该适配器`Update`中的方法`try` / `catch`块。

2. 如果捕获到异常，找到导致此错误的数据行。

3. 解决此问题在数据行 （您可以如果以编程方式或无效的行显示给用户进行修改），并再试一次更新 (<xref:System.Data.DataRow.HasErrors%2A>， <xref:System.Data.DataTable.GetErrors%2A>)。

## <a name="save-data-to-a-database"></a>将数据保存到数据库

调用`Update`TableAdapter 的方法。 传递包含要写入到数据库的值的数据表的名称。

### <a name="to-update-a-database-by-using-a-tableadapter"></a>若要使用 TableAdapter 更新数据库

- 将 TableAdapter`Update`中的方法`try` / `catch`块。 下面的示例演示如何更新的内容`Customers`表中`NorthwindDataSet`内`try` / `catch`块。

     [!code-csharp[VbRaddataSaving#9](../data-tools/codesnippet/CSharp/update-data-by-using-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataSaving#9](../data-tools/codesnippet/VisualBasic/update-data-by-using-a-tableadapter_1.vb)]

## <a name="see-also"></a>请参阅

- [将数据保存回数据库](../data-tools/save-data-back-to-the-database.md)