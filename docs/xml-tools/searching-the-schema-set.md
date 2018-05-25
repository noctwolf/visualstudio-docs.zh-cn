---
title: XML 架构资源管理器-搜索架构集
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: ec1395e0-d03c-4130-810d-f2db656937bd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c110344499281243628d633d005506af5cd801d0
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="search-the-schema-set"></a>搜索架构集

**XML 架构资源管理器**，您可以搜索架构集通过以下方式：

-   关键字搜索。

-   特定于架构的搜索。

## <a name="keyword-search"></a>关键字搜索

 通过输入中的子字符串执行关键字搜索**搜索架构集**文本框**XML 架构资源管理器**工具栏。

 ![XML 架构资源管理器关键字搜索](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")

 **XML 架构资源管理器**搜索架构集的以下属性：

-   与指定关键字匹配的任何 `name` 或 `ref` 特性。 可以按名称查找元素、 属性、 类型和等等。

-   包括语句的 `schemaLocation` 特性。

-   导入语句的 `namespace` 特性。

## <a name="schema-specific-search"></a>架构特定搜索

 **XML 架构资源管理器**还包括你可以通过使用的上下文菜单访问的内置搜索**XML 架构资源管理器**。 有关可用的上下文菜单的详细信息，请参阅[上下文菜单](../xml-tools/context-menus-xml-schema-explorer.md)。 您还可以通过以下方式执行特定于架构的搜索从起始视图;有关详细信息，请参阅中的"架构集详细信息"部分[起始视图](../xml-tools/start-view.md)主题。

## <a name="display-and-navigate-search-results"></a>显示和导航搜索结果

 完成搜索后，摘要结果窗格会添加到工具栏中，其中显示搜索的结果。 搜索结果中也将突出显示**XML 架构资源管理器**和由垂直滚动条上的刻度标记。 你可以通过使用导航搜索结果**转到下一个搜索结果**和**转到上一个搜索结果**上的摘要结果窗格中的按钮**XML 架构资源管理器**工具栏;通过使用键盘键**F3**和**Shift**+**F3**; 或单击滚动条中的刻度线。

 你可以向工作区添加搜索结果，通过单击**将突出显示的节点添加到工作区**摘要结果窗格上的按钮。

 ![XML 架构资源管理器搜索结果](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")

## <a name="clear-search-results"></a>清除搜索结果

 若要清除搜索结果，请单击**x**的摘要结果窗格上的按钮**XML 架构资源管理器**搜索工具栏。

## <a name="see-also"></a>请参阅

- [XML 架构资源管理器](../xml-tools/xml-schema-explorer.md)