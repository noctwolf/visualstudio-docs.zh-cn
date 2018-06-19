---
title: 如何： 将复数形式打开和关闭 （O R 设计器）
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a8c477ac276ce0ff9c292dc42ba2f5f7d1e53dd9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31921678"
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>如何： 将复数形式打开和关闭 （O/R 设计器）
默认情况下，当你将具有名称结尾 s 或从导致浏览器中的数据库对象拖动**服务器资源管理器**/**数据库资源管理器**到[LINQ to SQL 工具在 Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)，生成的实体类的名称从采用复数形式更改为单数。 这样可以更准确地表示实例化的实体类映射到单个数据记录的事实。 例如，将 Customers 表添加到 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]将声称名为 Customer 的实体类，因为该类将仅为一个客户保存数据。

> [!NOTE]
>  默认情况下，复数形式仅在 Visual Studio 的英语版本中启用。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-turn-pluralization-on-and-off"></a>打开和关闭复数形式

1.  在 **“工具”** 菜单上，单击 **“选项”**。

2.  在**选项**对话框框中，展开**数据库工具**。

    > [!NOTE]
    >  选择**显示所有设置**如果**数据库工具**节点不可见。

3.  单击**O/R 设计器**。

4.  设置**名称的复数形式**到**已启用** = **False**设置[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]，以便它不会更改类名称。

5.  设置**名称的复数形式**到**已启用** = **True**若要添加到的对象的类名称应用复数规则[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]。

## <a name="see-also"></a>请参阅

- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [在 Visual Studio 中访问数据](../data-tools/accessing-data-in-visual-studio.md)