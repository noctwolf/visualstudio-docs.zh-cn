---
title: DslTextTransform 命令
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: db916372691ce5e336e142aeb72288193e1ed807
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="the-dsltexttransform-command"></a>DslTextTransform 命令
DslTextTransform.cmd 是调用 TextTransform.exe 并运行包含常用选项的脚本。 你可以使用 DslTextTransformation.cmd 来自动执行的每夜生成你[!INCLUDE[dsl](../modeling/includes/dsl_md.md)]项目。 有关详细信息，请参阅[于 TextTransform 实用工具生成文件](../modeling/generating-files-with-the-texttransform-utility.md)。

 DslTextTransform.cmd 位于以下目录：

 **\<Visual Studio SDK 安装路径 > \VisualStudioIntegration\Tools\Bin**

 作为 DslTextTransform.cmd 的输入，你可以指定以下参数：

-   域模型项目的输出目录。

-   设计器的定义项目的输出目录。

-   文本模板文件的位置。

 DslTextTransform.cmd 处理指定的文本模板文件使用的默认指令处理器和程序集。 如果创建自定义指令处理器，你可以创建你自己调用 TextTransform.exe 的批处理文件。 在此批处理文件中，你可以指定你的程序集和关联的自定义指令处理器。