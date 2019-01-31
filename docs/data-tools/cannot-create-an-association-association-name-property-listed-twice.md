---
title: 无法创建关联 - 属性被列出了两次
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 3ced8bda-210e-4caf-9d8f-96cdbba19251
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: da5ee57dda360f9851737fe061ee02c6aeae4c8e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54954743"
---
# <a name="cannot-create-an-association-ltassociation-namegt---property-listed-twice"></a>无法创建关联 &lt;关联名称&gt; - 属性已列出两次

无法创建关联 \<关联名称>。 相同的属性已列出多次：\<属性名称>。

关联由在“关联编辑器”对话框中选择的“关联属性”定义。 对于关联中的每个类，属性只能列出一次。

消息中的属性在 Parent 类或 Child 类的“关联属性”中出现了多次。

## <a name="to-resolve-this-condition"></a>解决此问题的方法

- 检查消息并记下消息中指定的属性。

- 单击“确定”，关闭该消息框。

- 检查“关联属性”并移除重复项。

- 单击 **“确定”**。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [如何：创建 LINQ to SQL 类 （O/R 设计器） 之间的关联](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)