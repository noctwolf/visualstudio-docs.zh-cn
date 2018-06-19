---
title: 无法删除属性
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 80b5e40900cd8912b727270a46ebcf119c324f53
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31922862"
---
# <a name="the-property-property-name-cannot-be-deleted"></a>属性\<属性名称 > 不能被删除

属性\<属性名称 > 无法删除，因为它被设置为**鉴别器属性**之间的继承\<类名称 > 和\<类名称 >

所选的属性被设置为**鉴别器属性**错误消息中指示的类之间的继承。 如果属性参与数据类之间的继承配置，则无法删除这些属性。

设置**鉴别器属性**为数据类，可以成功删除删除的所需的属性的另一个属性。

## <a name="to-correct-this-error"></a>更正此错误

1. 在 O/R 设计器中选择连接错误消息中指示的数据类的继承连线。

2. 设置**鉴别器**为另一个属性的属性。

3. 再次尝试删除该属性。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)