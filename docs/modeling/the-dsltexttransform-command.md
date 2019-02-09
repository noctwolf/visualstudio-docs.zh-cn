---
title: DslTextTransform 命令
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 89d83da450014ebf29e2882438d27f9284c9bbbb
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55939029"
---
# <a name="the-dsltexttransform-command"></a>DslTextTransform 命令
DslTextTransform.cmd 是一个脚本调用 TextTransform.exe 和运行使用常用的选项。 可以使用 DslTextTransformation.cmd 来自动执行的每夜生成您[!INCLUDE[dsl](../modeling/includes/dsl_md.md)]项目。 有关详细信息，请参阅[使用 TextTransform 实用工具生成文件](../modeling/generating-files-with-the-texttransform-utility.md)。

 DslTextTransform.cmd 位于以下目录中：

 **\<Visual Studio SDK 安装路径 > \VisualStudioIntegration\Tools\Bin**

 作为输入 DslTextTransform.cmd，可以指定以下参数：

- 域模型项目的输出目录。

- 设计器定义项目的输出目录。

- 文本模板文件的位置。

  DslTextTransform.cmd 处理指定的文本模板文件使用默认指令处理器和程序集。 如果创建自定义指令处理器，您可以创建自己调用 TextTransform.exe 的批处理文件。 在此批处理文件中，可以指定您的程序集和关联的自定义指令处理器。