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
ms.openlocfilehash: 6ed6b14f64d16d1f18d4b358761169c3d424cee8
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174057"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>该属性&lt;属性名称&gt;不能删除，因为它参与了关联&lt;关联名称&gt;

所选的属性设置为**关联属性**错误消息中指示的类之间的关联。 如果属性参与了数据类之间的关联，则无法删除。

设置**关联属性**到不同的数据类可以成功删除删除所需的属性的属性。

## <a name="to-correct-this-error"></a>更正此错误

1. 在选择的关联连线**O/R 设计器**连接错误消息中指示的数据类。

2. 双击该连线以打开**关联编辑器**对话框。

3. 删除属性**关联属性**。

4. 再次尝试删除该属性。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)