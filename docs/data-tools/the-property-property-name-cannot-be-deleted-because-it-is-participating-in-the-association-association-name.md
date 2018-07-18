---
title: 无法删除属性，因为它参与关联
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 98f95c489758b808ae7a210f7d83332f84571d1f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924134"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>属性&lt;属性名称&gt;无法删除，因为它参与关联&lt;关联名称&gt;

所选的属性被设置为**关联属性**错误消息中指示的类之间关联。 如果属性参与了数据类之间的关联，则无法删除。

设置**关联属性**为数据类，可以成功删除删除的所需的属性的另一个属性。

## <a name="to-correct-this-error"></a>更正此错误

1. 在 O/R 设计器中选择连接错误消息中指示的数据类的关联连线。

2. 双击该连线以打开**关联编辑器**对话框。

3. 删除从属性**关联属性**。

4. 再次尝试删除该属性。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)