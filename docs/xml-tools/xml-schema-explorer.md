---
title: XML 架构资源管理器
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 2fc39e98-b194-456b-a452-cfafb0a52d66
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 07c5ba8d28a053b83481cf24e3bc1e450c28844e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60050057"
---
# <a name="xml-schema-explorer"></a>XML 架构资源管理器

**XML 架构资源管理器**集成了 Microsoft Visual Studio 和 XML 编辑器来使你能够使用 XML 架构定义语言 (XSD) 架构。 当打开 XML 架构文件时**架构集**节点显示在**XML 架构资源管理器**。 目标文件，以及通过引用的任何文件的所有包括、 导入，或重新定义架构`include`或`import`语句，也会显示在**XML 架构资源管理器**。

 **XML 架构资源管理器**使您能够执行以下操作：

- 快速了解架构集。

- 浏览和导航树。

- 执行关键字搜索和架构特定的搜索。 有关详细信息，请参阅[搜索架构集](../xml-tools/searching-the-schema-set.md)。

- 将搜索结果添加到图形视图或内容模型视图

- 按文档顺序、类型或名称对树进行排序。 有关详细信息，请参阅[排序、 筛选和分组](../xml-tools/sorting-filtering-and-grouping-xml-schema-explorer.md)。

- XML 编辑器打开并跳转到 XSD 文件中的代码位置。 有关详细信息，请参阅[与 XML 编辑器集成](../xml-tools/integration-with-xml-editor.md)。

- 为全局元素生成示例 XML。

**XML 架构资源管理器**提供架构集通过树视图的分层视图。 **XML 架构资源管理器**还提供了搜索、 筛选、 导航和排序。 访问**XML 架构资源管理器**，执行下列操作之一：

- 如果你位于[起始视图](../xml-tools/start-view.md)，单击**XML 架构资源管理器**链接。

- 如果你位于[关系图视图](../xml-tools/graph-view.md)或[内容模型视图](../xml-tools/content-model-view.md)和工作区中有节点，请使用上下文 （右键单击） 菜单选择**XML 架构资源管理器**。

- 您还可以选择**XML 架构资源管理器**从**视图**菜单。

- 您可以访问**XML 架构资源管理器**从 *.vb*具有与关联的 Visual Basic XML 文本的文件 *.xsd*文件。 若要查看架构中设置**XML 架构资源管理器**，右键单击 XML 文本或导入的 XML 命名空间中的 XML 节点，然后选择**在架构资源管理器中显示**命令。 有关详细信息，请参阅[集成的 XML 文本与 XML 架构资源管理器](../xml-tools/integration-of-xml-literals-with-xml-schema-explorer.md)。

## <a name="tree-view"></a>树视图
 **XML 架构资源管理器**显示预编译架构在树状结构中设置的信息。 树结构的组织方式如下：

- 位于顶级的是架构集节点。

- 第二级中包含命名空间。

- 第三级中包含文件。

- 第四级中包含全局节点， 其中可包括元素、组、复杂类型、简单类型、特性、特性组以及 `include`、`import` 和 `redefine` 语句。

下面是树结构的示例：

![XML 架构资源管理器](../xml-tools/media/xmlschemaexplorer.gif)

## <a name="selection-and-activation"></a>选择和激活
 若要突出显示并选择节点，请在架构资源管理器中单击一次。

 若要激活的节点，双击它，或按**Enter**时选择的节点。

- 激活某节点时会打开在其中定义该节点的文件（如果文件尚未打开）并在文件中选择该节点。

- 激活文件节点时会打开选定文件（如果该文件尚未打开）并突出显示 `<schema>` 节点。

- 激活架构集或命名空间节点不会执行任何操作。

## <a name="drag-and-drop-nodes"></a>拖放到节点
 可以将全局节点、文件节点和命名空间节点拖放到 XSD 设计器视图上。 如果当前视图是[起始视图](../xml-tools/start-view.md)，拖动到该视图的节点将会打开[关系图视图](../xml-tools/graph-view.md)。 如果当前视图是[内容模型视图](../xml-tools/content-model-view.md)或图形视图，视图将不会在你放到它上面的节点。

 在视图上的文件放到在文件中将添加所有全局节点[XSD 设计器工作区](../xml-tools/xml-schema-designer-workspace.md)。 将命名空间放置在视图上将向工作区添加命名空间中的所有全局节点。 工作区在所有视图之间共享。

 不能拖放或导入本地节点。

## <a name="see-also"></a>请参阅

- [如何：从 XML 架构资源管理器向工作区添加节点](../xml-tools/how-to-add-nodes-to-the-workspace-from-the-xml-schema-explorer.md)