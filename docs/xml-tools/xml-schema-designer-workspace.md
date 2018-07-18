---
title: XML 架构设计器工作区
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 588fa495-fe7f-4b16-8a9f-6b6b8d2d502a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 317588e4d6c81a13a18c036a040508a1adebafcb
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
ms.locfileid: "34476709"
---
# <a name="xml-schema-designer-workspace"></a>XML 架构设计器工作区

XML 架构设计器（XSD 设计器）是一个图形工具，可帮助您浏览 XML 架构。 除了[XML 架构资源管理器](../xml-tools/xml-schema-explorer.md)，它可以浏览和导航 XML 架构树以及执行搜索，XSD 设计器提供了三个视图，可用于浏览 XSD 架构的更多详细信息。 起始视图，它是 XSD 设计器的启动点；从起始视图可以导航到 XSD 设计器的其他视图，并查看架构集的详细信息。 图形视图，利用它可查看架构集的概览以及架构节点之间的关系。 内容模型视图，它以图形表示形式提供局部和全局架构节点（包括简单类型和复杂类型、元素、组、特性及特性组）的详细信息。

若要开始浏览您感兴趣的节点，必须将它们添加到工作区中。 工作区在所有视图之间共享。

## <a name="add-nodes-to-the-workspace"></a>将节点添加到工作区

可通过以下方法将节点添加到工作区中：

-   中的"架构集详细信息"部分[起始视图](../xml-tools/start-view.md)，单击**添加**全局节点类型旁边的链接。

-   全局节点、 文件节点和从命名空间节点拖放**XML 架构资源管理器**拖放到任意三个视图。 有关详细信息，请参阅"拖动和删除节点"一节中的[XML 架构资源管理器](../xml-tools/xml-schema-explorer.md)。

-   使用中的上下文菜单**XML 架构资源管理器**。 有关详细信息，请参阅[上下文菜单](../xml-tools/context-menus-xml-schema-explorer.md)。

-   在 XSD 资源管理器中执行搜索并单击**将突出显示的节点添加到工作区**摘要结果窗格上的按钮。 有关详细信息，请参阅[搜索架构集](../xml-tools/searching-the-schema-set.md)。

## <a name="switch-views"></a>切换视图

若要切换视图，请使用下列工具之一：

-   XSD 设计器工具栏。

-   内容模型视图和图形视图的上下文菜单。

-   起始视图页上的水印、空内容模型视图上的水印或图形视图上的水印。

-   热键： **Ctrl**+**1**起始视图中，为**Ctrl**+**2**对于关系图视图中，和**Ctrl**+**3**内容模型视图。