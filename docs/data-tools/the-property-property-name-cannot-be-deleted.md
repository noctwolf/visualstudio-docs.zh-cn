---
title: 不能删除属性
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
ms.openlocfilehash: 7e85860de7494ae7d93ad37bd0a115fa786f0a87
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174008"
---
# <a name="the-property-property-name-cannot-be-deleted"></a>该属性\<属性名称 > 不能删除

该属性\<属性名称 > 不能删除，因为它被设置为**鉴别器属性**之间的继承\<类名称 > 和\<类名称 >

所选的属性设置为**鉴别器属性**类之间的继承所指示的错误消息中。 如果属性参与数据类之间的继承配置，则无法删除这些属性。

设置**鉴别器属性**到不同的数据类可以成功删除删除所需的属性的属性。

## <a name="to-correct-this-error"></a>更正此错误

1. 在中**O/R 设计器**，选择连接的数据类的继承连线所示的错误消息。

2. 设置**鉴别器**为另一个属性的属性。

3. 再次尝试删除该属性。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)