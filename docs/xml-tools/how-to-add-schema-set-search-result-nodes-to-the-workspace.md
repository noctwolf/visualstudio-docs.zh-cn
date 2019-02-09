---
title: 将 XML 架构集搜索结果节点添加到工作区
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7cb8e66292a1cdb393401d180bd8b9f8691dc8f0
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55913923"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>如何：将架构集搜索结果节点添加到工作区

本主题说明如何以突出显示的节点添加**XML 架构资源管理器**作为工作区中的关键字搜索结果。

> [!NOTE]
> 只能将全局节点可以添加到[工作区](../xml-tools/xml-schema-designer-workspace.md)。


 此示例使用示例[采购订单架构](../xml-tools/sample-xsd-file-purchase-order-schema.md)。

## <a name="to-add-schema-set-result-nodes"></a>添加架构集结果节点

1.  按照中的步骤[如何：创建和编辑 XSD 架构文件](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)。

2.  中的搜索文本框中键入"purchaseOrder" [XML 资源管理器](../xml-tools/xml-schema-explorer.md)工具栏，然后单击搜索按钮。

     ![XML 架构资源管理器关键字搜索](../xml-tools/media/schemaexplorersearch.gif)

     搜索结果中突出显示**XML 架构资源管理器**和按垂直滚动条上的刻度标记。

3.  单击将搜索结果添加到工作区**突出显示的节点添加到工作区**摘要结果窗格上的按钮。

     ![XML 架构资源管理器搜索结果](../xml-tools/media/schemaexplorersearchresult.gif)

     `purchaseOrder`节点和`PurchaseOrderType`节点的设计图面上显示彼此[关系图视图](../xml-tools/graph-view.md)。 因为这两个节点相关（`purchaseOrder` 元素属于 `PurchaseOrderType` 类型），因此会在这两个节点之间绘制一个箭头。