---
title: 如何： 使用 XSLT 断点 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f262fa2b1822f74dc15b6f8599b88161c0a1cf8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-breakpoints-with-xslt"></a>如何： 使用 XSLT 使用断点

您可以在 XSLT 样式表中或 XML 源文档中设置断点。 如果在标记上设置了断点，则在开始执行时，断点将转到包含源代码行信息的下一条语句。

有关详细信息，请参阅[调试基础知识： 断点](../debugger/using-breakpoints.md)。

## <a name="set-a-breakpoint-in-a-style-sheet"></a>样式表中设置断点

在 XSLT 样式表的开始标记、结束标记和文本节点上都可以设置断点。 也可以在脚本块中的代码上设置断点。  
  
### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>在样式表中设置断点
  
1.  在“XML 编辑器”中打开样式表。  
  
2.  将光标置于断点位置，右键单击，指向**断点**，然后单击**插入断点**。  
  
3.  单击浏览浏览按钮 (**...**) 上**输入**字段的文档属性窗口。  
  
4.  找到 XML 源文档并单击**打开**。  
  
     此时将设置用于 XSLT 转换的源文档文件。  
  
5.  单击**调试 XSL** XML 编辑器工具栏上的按钮。  

## <a name="set-a-breakpoint-in-an-xml-source-document"></a>XML 源文档中设置断点

在 XML 源文档的元素、属性、命名空间节点、注释、处理指令和文本节点上都可以设置断点。 无法在文档节点上或在继承自父元素的命名空间节点设置断点。  

### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>在 XML 源文档中设置断点

1.  在 XML 编辑器中打开 XML 文档。  
  
2.  将光标置于断点位置，右键单击，指向**断点**，然后单击**插入断点**。  
  
3.  单击浏览浏览按钮 (**...**) 上**样式表**字段的文档属性窗口。  
  
4.  找到 XML 源文档并单击**打开**。  
  
     此时将设置用于 XSLT 转换的源文档文件。  
  
5.  单击**调试 XSL** XML 编辑器工具栏上的按钮。  
 
## <a name="see-also"></a>请参阅

[演练：调试 XSLT 样式表](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)