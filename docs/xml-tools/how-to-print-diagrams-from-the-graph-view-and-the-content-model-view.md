---
title: 从图形视图和 XML 架构设计器的内容模型视图打印关系图
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 7e1785e4-4aaf-4c66-8735-51e7ca035565
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d4710752c4825ce576b20a823735b5ed1e2ebad
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53900933"
---
# <a name="how-to-print-diagrams-from-the-graph-view-and-the-content-model-view"></a>如何：从图形视图和内容模型视图打印关系图

本主题介绍如何从图形视图或内容模型视图的 XML 架构设计器中打印关系图。

## <a name="to-print-diagrams-from-the-xml-schema-designer"></a>从 XML 架构设计器中打印关系图

1.  在 Visual Studio 中打开 XSD 文件并添加到某些节点[XML 架构设计器工作区](../xml-tools/xml-schema-designer-workspace.md)。

2.  通过使用关系图导出到 XPS 文件**关系图导出为图像**设计图面中的图形视图或内容模型视图的上下文菜单项。

     从图形视图导出关系图时，整个设计图面将导出到 XPS 文件。 当从内容模型视图导出关系图将多个节点出现在内容模型视图的设计图面上时，只有第一个节点将导出到 XPS 文件。

3.  通过使用 XPS 查看器，打印在 XPS 文件中保存的图像。

## <a name="see-also"></a>请参阅

- [图形视图](../xml-tools/graph-view.md)
- [内容模型视图](../xml-tools/content-model-view.md)
- [XML 架构设计器工作区](../xml-tools/xml-schema-designer-workspace.md)