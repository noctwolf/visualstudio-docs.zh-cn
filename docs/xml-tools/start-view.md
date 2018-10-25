---
title: XML 架构设计器起始视图
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: f25e7a2f-7469-4279-b2f4-ee2dfd4d3af1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 302c6574b8c09447f4b7e561118e60d200a3944f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49920667"
---
# <a name="start-view"></a>起始视图

起始视图是 XML 架构 (XSD) 设计器的启动点。 创建新的 XSD 文件时，您将最初看到起始视图。

起始视图包括两个主要部分*水印*并**架构集详细信息**窗格。 起始视图还包括在所有 XSD 设计器视图中都可用的工具栏。

![XML 架构设计器起始视图](../xml-tools/media/xsddesigner_startview.gif)

## <a name="watermark"></a>水印

水印窗格包含指向所有 XSD 设计器视图中，XML 编辑器的列表和**XML 架构资源管理器**。 如果架构集有错误，则列表的末尾会显示以下文本：“请使用‘错误列表’查看和修复架构集中的错误”[Use the Error List to view and fix the errors in the set]。

## <a name="schema-set-details"></a>架构集详细信息

**架构集详细信息**窗格列出全局架构节点类型，并显示在架构中有每种类型的实例数。 可以使用**添加**要将新节点添加到工作区的节点类型旁边的链接。

## <a name="toolbar"></a>Toolbar

可以在入门视图之间导航[内容模型视图](../xml-tools/content-model-view.md)并[关系图视图](../xml-tools/graph-view.md)从 XML 架构设计器工具栏。

![XML 架构设计器工具栏](../xml-tools/media/xsdstartviewtoolbar.gif)

当起始视图处于活动状态时，会在 XSD 设计器工具栏中启用以下按钮：

|选项|描述|
|-|-----------------|
|**显示起始视图**|切换到起始视图。 可以使用键盘快捷方式访问此视图： **Ctrl**+**1**。|
|**显示内容模型视图**|切换到内容模型视图。 可以使用键盘快捷方式访问此视图： **Ctrl**+**2**。|
|**显示图形视图**|切换到图形视图。 可以使用键盘快捷方式访问此视图： **Ctrl**+**3**。|

## <a name="see-also"></a>请参阅

- [XML 架构资源管理器](../xml-tools/xml-schema-explorer.md)
- [图形视图](../xml-tools/graph-view.md)
- [内容模型视图](../xml-tools/content-model-view.md)
- [XML 编辑器](../xml-tools/xml-editor.md)