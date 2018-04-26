---
title: 如何：计算 XPath 表达式
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f2956e0c19e7cf50fdde39765bc5b26112986b84
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-evaluate-an-xpath-expression"></a>如何：计算 XPath 表达式

你可以使用计算 XPath 表达式**快速监视**对话框。 XPath 表达式必须符合 W3C XPath 1.0 建议。 当前 XSLT 上下文 — 即`self::node()`中的节点**局部变量**窗口 — 为 XPath 表达式提供计算上下文。

 下表说明在计算 XPath 表达式时支持的函数：

-   支持内置 XPath 函数。

-   不支持内置 XSLT 函数。

-   不支持用户定义函数。

> [!NOTE]
> 下面的过程使用的 belowAvg.xsl 和 books.xml 文件[演练： 调试 XSLT 样式表](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)主题。

## <a name="to-evaluate-an-xpath-expression"></a>计算 XPath 表达式

1.  在 `xsl:if` 开始标记处插入断点。

2.  单击**调试 XSL** XML 编辑器工具栏上的按钮。

     调试程序在 `xsl:if` 标记处开始和中断。

3.  右键单击并选择**快速监视**。

     **快速监视**对话框随即显示。

4.  输入`./price/text()`中**表达式**字段**快速监视**对话框中，单击**重新计算**。

     当前 book 节点的价格将出现在**值**框。

5.  更改的 XPath 表达式`./price/text() < $bookAverage`单击**重新计算**。

     **值**框显示 XPath 表达式计算结果为`true`。

## <a name="see-also"></a>请参阅

- [调试 XSLT](../xml-tools/debugging-xslt.md)