---
title: 您添加到设计器的对象使用与当前使用的设计器不同的数据连接
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 33a6083fb9e52ebdafbc827fc19666c1df9a3f7e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="the-objects-you-are-adding-to-the-designer-use-a-different-data-connection-than-the-designer"></a>添加到设计器的对象使用不同的数据连接与设计器

要添加到设计器中的对象使用的数据连接与设计器当前所用的数据连接不同。 是否要替换设计器使用的连接?

在将项添加到[!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)]（[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]）时，所有项都使用同一个共享数据连接。 （设计图面表示 <xref:System.Data.Linq.DataContext>，它将单个连接用于图面上的所有对象。）如果添加到设计器中的对象使用的数据连接与设计器当前使用的数据连接不同，则会出现此消息。 若要解决此错误，可以选择保持现有连接。 如果选择这样做，则不会添加所选对象。 您也可以选择添加对象并将 <xref:System.Data.Linq.DataContext> 连接重置为新的连接。

> [!NOTE]
> 如果你单击**是**上的所有实体都类[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]都映射到新的连接。

## <a name="to-replace-the-existing-connection-with-the-connection-used-by-the-selected-object"></a>将现有连接替换为所选对象使用的连接

- 单击 **“是”**。

    所选对象将添加到 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]中，并且 DataContext.Connection 设置为新连接。

## <a name="to-continue-to-use-the-existing-connection-and-cancel-adding-the-selected-object"></a>继续使用现有连接并取消添加所选对象的操作

- 单击“否” 。

    操作被取消。 DataContext.Connection 仍然设置为现有连接。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
