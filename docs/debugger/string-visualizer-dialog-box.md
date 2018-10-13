---
title: 字符串可视化工具中查看字符串 |Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
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
ms.openlocfilehash: 689889e98a5a9b69a49e73ccea73f30fc3c25249
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49274308"
---
# <a name="view-strings-in-a-string-visualizer-in-visual-studio"></a>在 Visual Studio 中的字符串可视化工具中查看字符串

虽然 Visual Studio 中进行调试，但可以使用内置字符串可视化工具查看字符串。 字符串可视化工具显示数据提示或调试器窗口太长的字符串。 它还可以帮助您识别格式不正确的字符串。

内置字符串可视化工具包括纯文本、 XML、 HTML 和 JSON 选项。 您还可以从打开几个其他类型，如 WPF 对象可视化工具**自动**或其他调试器窗口。

## <a name="open-a-string-visualizer"></a>打开字符串可视化工具

若要打开字符串可视化工具，您必须暂停在调试过程。 悬停在具有纯文本、 XML、 HTML 或 JSON 字符串值，并选择放大镜图标的变量![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "可视化工具图标")。

![打开字符串可视化工具](../debugger/media/dbg-tips-string-visualizers.png "打开字符串可视化工具")

## <a name="view-string-visualizer-data"></a>查看字符串可视化工具数据

在字符串可视化工具窗口中，**表达式**字段显示的变量或表达式要悬停，并**值**字段显示的字符串值。 

空白**值**意味着所选的可视化工具不能识别该字符串。 例如， **XML 可视化工具**显示空白**值**无 XML 标记，一个文本字符串或 JSON 字符串。 

若要查看所选的可视化工具无法识别的字符串，请选择**文本可视化工具**。 **文本可视化工具**显示纯文本。

### <a name="view-json-string-data"></a>查看 JSON 字符串数据

格式正确的 JSON 字符串看起来类似于下图中的 JSON 可视化工具。 JSON 格式不正确可能会显示错误图标 （或无法识别的则为空）。 若要标识 JSON 错误，请复制并粘贴字符串到 JSON linting 工具如[JSLint](https://www.jslint.com/)。

![JSON 字符串可视化工具](../debugger/media/dbg-tips-string-visualizer-json.png "JSON 字符串可视化工具")

### <a name="view-xml-string-data"></a>查看 XML 字符串数据

格式正确的 XML 字符串看起来类似于下图中的 XML 可视化工具。 如果无法识别，XML 格式不正确可能会显示不包含 XML 标记或为空。

![XML 字符串可视化工具](../debugger/media/dbg-string-visualizers-xml.png "XML 字符串可视化工具")

### <a name="view-html-string-data"></a>查看 HTML 字符串数据

格式正确的 HTML 字符串出现像在浏览器的呈现将如以下插图所示。 HTML 格式不正确可能会以明文形式显示。

![HTML 字符串可视化工具](../debugger/media/dbg-string-visualizers-html.png "HTML 字符串可视化工具")

## <a name="see-also"></a>请参阅  
 [创建自定义可视化工具 （C#、 Visual Basic）](../debugger/create-custom-visualizers-of-data.md)