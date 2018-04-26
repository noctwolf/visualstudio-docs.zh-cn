---
title: 从关系图视图和 XML 架构设计器的内容模型视图打印关系图
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 7e1785e4-4aaf-4c66-8735-51e7ca035565
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e1bdcada913b926b27ccffdf1d7c0a6b2488ead8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-print-diagrams-from-the-graph-view-and-the-content-model-view"></a>如何：从图形视图和内容模型视图打印关系图

本主题介绍如何从图形视图或内容模型视图的 XML 架构设计器中打印关系图。

## <a name="to-print-diagrams-from-the-xml-schema-designer"></a>从 XML 架构设计器中打印关系图

1.  在 Visual Studio 中打开 XSD 文件并添加到某些节点[XML 架构设计器工作区](../xml-tools/xml-schema-designer-workspace.md)。

2.  将图示导出到 XPS 文件，通过使用**将关系图导出为图像...** 的图形视图或内容模型视图的设计图面中的上下文菜单项。

     当您从图形视图导出关系图时，整个设计图面将被导出到 XPS 文件。 当您从内容模型视图导出关系图，并且多个节点显示在内容模型视图的设计图面上时，只有第一节点会导出到 XPS 文件。

3.  通过使用 XPS 查看器，打印在 XPS 文件中保存的图像。

## <a name="see-also"></a>请参阅

- [图形视图](../xml-tools/graph-view.md)
- [内容模型视图](../xml-tools/content-model-view.md)
- [XML 架构设计器工作区](../xml-tools/xml-schema-designer-workspace.md)