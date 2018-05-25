---
title: 如何：在视图和 XML 编辑器之间切换
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: cb69fbbd-d99c-439e-9498-5df9050f8df0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0b0eb90f2ead313ce94d609d71385b595f3e964b
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="how-to-switch-between-views-and-the-xml-editor"></a>如何： 视图和 XML 编辑器之间切换

本主题演示如何在 XML 架构设计器（XSD 设计器）视图和 XML 编辑器之间进行切换。 此示例使用[采购订单架构](../xml-tools/sample-xsd-file-simple-schema.md)。

## <a name="to-switch-between-the-views-and-the-xml-editor"></a>在视图和 XML 编辑器之间切换

1.  若要创建和编辑新的 XML 架构文件，请按照中的步骤[如何： 创建和编辑 XSD 架构文件](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)。

2.  若要从 XML 编辑器中切换到 XML 架构设计器中，右键单击任意位置在 XML 编辑器中，然后选择**视图设计器**。

3.  若要切换到使用水印的图形视图，请单击**使用关系图视图以查看节点之间的关系**起始视图上的链接。

4.  拖动`USAddress`节点从**XML 架构资源管理器**拖放到关系图视图。 右键单击`USAddress`节点在图形视图，选择**在内容模型视图中显示**上下文菜单中。

     将显示包含 `USAddress` 节点详细信息的内容模型视图。

5.  若要从使用工具栏上的内容模型视图切换到起始视图，请单击**起始视图**XSD 工具栏上的按钮。

6.  若要使用热键在视图之间切换，请按**Ctrl**+**1**的启动视图中， **Ctrl**+**2**对于关系图视图中，和**Ctrl**+**3**内容模型视图。

7.  若要从内容模型视图转到 XML 编辑器，右键单击节点并选择**查看代码**上下文菜单中。