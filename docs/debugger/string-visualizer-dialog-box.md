---
title: 字符串可视化工具中查看字符串 |Microsoft Docs
ms.custom: ''
ms.date: 07/11/2017
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.stringviewer
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- string visualizer
- visualizers, string
ms.assetid: 080fd8f1-72b0-461f-8451-3c84d5dc51df
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca6e4519a85659b36e5cf6baebaadd1d1c626f1a
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151029"
---
# <a name="view-strings-in-a-string-visualizer-in-visual-studio"></a>在 Visual Studio 中的字符串可视化工具中查看字符串
在调试时可以打开太长，若要查看在数据提示或调试器窗口中查看字符串到字符串可视化工具。 在许多情况下，可视化工具可以帮助您识别格式不正确的字符串。

内置的标准字符串可视化工具包括纯文本、 XML、 HTML 和 JSON。 例如，在调试器中显示的 WPF 对象的几种其他类型的 windows 等**自动**窗口中，您还可以打开可视化工具。

## <a name="open-a-string-visualizer"></a>打开字符串可视化工具

若要查看纯文本、 XML、 HTML 或 JSON 字符串，请单击放大镜图标![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "可视化工具图标")当悬停在包含一个字符串值的变量。 你必须看到放大镜图标在调试器中暂停。

![打开字符串可视化工具](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

## <a name="view-string-data"></a>查看字符串数据

**表达式**字符串可视化工具中的字段在调试器中显示的当前变量或悬停在表达式。

**值**字段显示的字符串值。 文本可视化工具显示纯文本。

空白**值**指示特定的可视化工具无法识别此字符串类型。 例如，XML 可视化工具显示空白**值**的简单文本字符串 （具有无 XML 标记） 或 JSON 格式字符串。 如果你需要在可视化工具中查看无法识别的字符串，使用文本可视化工具。

### <a name="view-json-string-data"></a>查看 JSON 字符串数据

格式正确的 JSON 字符串将显示类似于下图中的 JSON 可视化工具。 JSON 格式不正确可能会显示错误图标 （或无法识别的则为空）。 如果看到一个错误图标，复制并粘贴 JSON 字符串到 JSON linting 工具如[JSLint](https://www.jslint.com/)以识别 JSON 错误。

![JSON 字符串可视化工具](../debugger/media/dbg-tips-string-visualizer-json.png "JSON 字符串可视化工具")

### <a name="view-xml-string-data"></a>查看 XML 字符串数据

格式正确的 XML 字符串将显示类似于下图中的 XML 可视化工具。 XML 格式不正确可能会显示不带有 XML 标记 （或无法识别的则为空）。

![XML 字符串可视化工具](../debugger/media/dbg-string-visualizers-xml.png "XML 字符串可视化工具")

### <a name="view-html-string-data"></a>查看 HTML 字符串数据

格式正确的 HTML 字符串看起来类似于将看到是否字符串将呈现在浏览器中，如下图中所示的视图。 HTML 格式不正确可能会以明文形式显示。

![HTML 字符串可视化工具](../debugger/media/dbg-string-visualizers-html.png "HTML 字符串可视化工具")

## <a name="see-also"></a>请参阅  
 [创建自定义可视化工具 （C#、 Visual Basic）](../debugger/create-custom-visualizers-of-data.md)