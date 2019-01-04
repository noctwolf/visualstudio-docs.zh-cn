---
title: 如何：在视图和 XML 编辑器之间切换
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: cb69fbbd-d99c-439e-9498-5df9050f8df0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 09ad752dc87ea322396d6e6513593d71a7554b98
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53936238"
---
# <a name="how-to-switch-between-views-and-the-xml-editor"></a>如何：视图和 XML 编辑器之间切换

本主题演示如何在 XML 架构设计器（XSD 设计器）视图和 XML 编辑器之间进行切换。 此示例使用[采购订单架构](../xml-tools/sample-xsd-file-simple-schema.md)。

## <a name="to-switch-between-the-views-and-the-xml-editor"></a>在视图和 XML 编辑器之间切换

1.  若要创建和编辑新的 XML 架构文件，请按照中的步骤[如何：创建和编辑 XSD 架构文件](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)。

2.  若要从 XML 编辑器中切换到 XML 架构设计器中，右键单击任意位置在 XML 编辑器中，并选择**视图设计器**。

3.  若要切换到使用水印的图形视图，请单击**使用关系图视图来查看节点之间的关系**起始视图上的链接。

4.  拖动`USAddress`节点从**XML 架构资源管理器**拖至关系图视图上。 右键单击`USAddress`在关系图视图中，选择节点**在内容模型视图中显示**的上下文菜单中。

     将显示包含 `USAddress` 节点详细信息的内容模型视图。

5.  若要从使用工具栏在内容模型视图切换到起始视图，请单击**起始视图**XSD 工具栏上的按钮。

6.  若要使用热键在视图之间切换，按**Ctrl**+**1**的启动视图中， **Ctrl**+**2**对于关系图视图中，并**Ctrl**+**3**内容模型视图。

7.  若要从内容模型视图转到 XML 编辑器中，右键单击节点并选择**查看代码**的上下文菜单中。