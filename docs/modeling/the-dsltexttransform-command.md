---
title: "DslTextTransform 命令 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 24a3f292633b915678bad232a4a671c7906e15cb
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="the-dsltexttransform-command"></a>DslTextTransform 命令
DslTextTransform.cmd 是调用 TextTransform.exe 并运行包含常用选项的脚本。 你可以使用 DslTextTransformation.cmd 来自动执行的每夜生成你[!INCLUDE[dsl](../modeling/includes/dsl_md.md)]项目。 有关详细信息，请参阅[于 TextTransform 实用工具生成文件](../modeling/generating-files-with-the-texttransform-utility.md)。  
  
 DslTextTransform.cmd 位于以下目录：  
  
 **\<Visual Studio SDK Installation Path>\VisualStudioIntegration\Tools\Bin**  
  
 作为 DslTextTransform.cmd 的输入，你可以指定以下参数：  
  
-   域模型项目的输出目录。  
  
-   设计器的定义项目的输出目录。  
  
-   文本模板文件的位置。  
  
 DslTextTransform.cmd 处理指定的文本模板文件使用的默认指令处理器和程序集。 如果创建自定义指令处理器，你可以创建你自己调用 TextTransform.exe 的批处理文件。 在此批处理文件中，你可以指定你的程序集和关联的自定义指令处理器。