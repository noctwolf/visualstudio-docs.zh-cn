---
title: 编辑 XSLT 样式表
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 080bed0f-0ca9-4be7-aecd-6bdaebc04007
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d98fbf2a1041260370946a059599a601f57c482c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867402"
---
# <a name="edit-xslt-style-sheets"></a>编辑 XSLT 样式表

“XML 编辑器”还可以用于编辑 XSLT 样式表。 可以利用默认的编辑器功能，例如 IntelliSense、大纲、XML 代码段等。 此外，还提供了一些新功能，使 XSLT 中的开发更加容易。

## <a name="xslt-features"></a>XSLT 功能
 下表介绍使用 XSLT 样式表时的特定功能。

 **语法着色**

 XSLT 关键字，如`template`， `match`，依此类推，显示在指定的 XSLT 关键字颜色**字体和颜色**设置。

 **波浪形下划线**

 XML 编辑器使用已安装*xslt.xsd*文件验证 XSLT 样式表。 验证错误以蓝色的波浪形下划线显示。 “XML 编辑器”还在后台编译样式表，并使用相应的波浪形下划线报告编译器错误或警告。

 **对脚本块的支持**

 XSLT 调试程序支持脚本块中的代码，这样，你可以设置断点并逐行执行脚本块代码。

 **查看 XSLT 输出**

 可以在“XML 编辑器”中执行 XSL 转换并查看输出。 有关更多信息，请参见[如何：从 XML 编辑器中执行 XSLT 转换](../xml-tools/how-to-execute-an-xslt-transformation-from-the-xml-editor.md)。

 **调试 XSLT**

 可以在“XML 编辑器”中从 XSLT 文件启动 XSLT 调试程序。 调试程序支持在 XSLT 文件中设置断点、查看 XSLT 执行状态等。 将光标置于 XSLT 变量上，可以显示包含变量值的工具提示。 调试程序可以用于调试样式表，也可以用于调试从另一个应用程序调用的已编译 XSLT 转换。 有关详细信息，请参阅[调试 XSLT](../xml-tools/debugging-xslt.md)。

## <a name="see-also"></a>请参阅

- [XML 编辑器](../xml-tools/xml-editor.md)