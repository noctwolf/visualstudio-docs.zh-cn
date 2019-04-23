---
title: XML 架构设计器工作区
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 588fa495-fe7f-4b16-8a9f-6b6b8d2d502a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e6dde8eee0c21f41cb21acf97fb68961dd0beee7
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60107341"
---
# <a name="xml-schema-designer-workspace"></a>XML 架构设计器工作区

XML 架构设计器（XSD 设计器）是一个图形工具，可帮助您浏览 XML 架构。 除了[XML 架构资源管理器](../xml-tools/xml-schema-explorer.md)、 可用于浏览和 XML 架构树中导航并执行搜索、 XSD 设计器提供了三个视图，使您能够浏览 XSD 架构的更多详细信息。 起始视图，它是 XSD 设计器的启动点；从起始视图可以导航到 XSD 设计器的其他视图，并查看架构集的详细信息。 图形视图，利用它可查看架构集的概览以及架构节点之间的关系。 内容模型视图，它以图形表示形式提供局部和全局架构节点（包括简单类型和复杂类型、元素、组、特性及特性组）的详细信息。

若要开始浏览您感兴趣的节点，必须将它们添加到工作区中。 工作区在所有视图之间共享。

## <a name="add-nodes-to-the-workspace"></a>将节点添加到工作区

可通过以下方法将节点添加到工作区中：

- 在"架构集详细信息"部分中的[起始视图](../xml-tools/start-view.md)，单击**添加**全局节点类型旁边的链接。

- 拖放到全局节点、 文件节点和命名空间节点从**XML 架构资源管理器**到的任何三个视图。 有关详细信息，请参阅中的"拖放节点"部分[XML 架构资源管理器](../xml-tools/xml-schema-explorer.md)。

- 使用中的上下文 （右键单击） 菜单**XML 架构资源管理器**。 有关详细信息，请参阅[上下文菜单](../xml-tools/context-menus-xml-schema-explorer.md)。

- 在 XSD 资源管理器中执行搜索，并单击**突出显示的节点添加到工作区**摘要结果窗格上的按钮。 有关详细信息，请参阅[搜索架构集](../xml-tools/searching-the-schema-set.md)。

## <a name="switch-views"></a>切换视图

若要切换视图，请使用下列工具之一：

- XSD 设计器工具栏。

- 内容模型视图和图形视图的上下文 （右键单击） 菜单。

- 起始视图页上的水印、空内容模型视图上的水印或图形视图上的水印。

- 热键：**Ctrl**+**1**起始视图中，对于**Ctrl**+**2**关系图视图和**Ctrl**+ **3**内容模型视图。