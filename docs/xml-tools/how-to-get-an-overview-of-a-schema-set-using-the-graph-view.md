---
title: 如何： 获取设计器的 XML 架构中使用图形视图架构集概述
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8be2666316bdc4d64d4f3dd4ec52c5104a1af5cc
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>如何： 获取架构集使用图形视图的概述

本主题介绍如何使用[图形视图](../xml-tools/graph-view.md)若要查看架构集以及节点之间的关系中的节点的高级视图。

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>创建新的 XSD 文件并显示内容模型视图中的根元素

1.  创建新的 XML 架构文件并将文件另存*Relationships.xsd*。

2.  单击**使用 XML 编辑器查看和编辑基础 XML 架构文件**起始视图上的链接。

3.  复制 XML 架构示例代码从[示例 XML 架构： 关系](../xml-tools/sample-xsd-file-relationships.md)并将其以替换默认情况下，已将它们添加到新 XSD 文件的代码粘贴。

4.  右键单击任意位置在 XML 编辑器中，然后选择**视图设计器**。

5.  选择从图形视图**XSD 工具栏**。

6.  选择**架构集**中的节点**XML 架构资源管理器**并拖动该节点在图形视图的设计图面。 您应当会看到所有全局节点，以及连接有关系节点的箭头。

     ![图形视图](../xml-tools/media/relationshipingraphview.gif "RelationshipInGraphView")

7.  单击设计图面上的任何节点并查看痕迹栏，以了解所选节点在架构集中的位置。

8.  右击设计图面并选择上的任何元素节点**生成示例 XML**若要查看 XML 实例文档。