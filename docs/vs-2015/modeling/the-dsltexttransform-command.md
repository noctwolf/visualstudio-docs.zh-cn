---
title: DslTextTransform 命令 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, commands
ms.assetid: 7d025d0b-6543-4a49-9f6b-8b8cfcad77ee
caps.latest.revision: 32
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 8a565fa6226348a1fe1b6dcfcbb67f704e74abc8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479729"
---
# <a name="the-dsltexttransform-command"></a>DslTextTransform 命令
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[DslTextTransform 命令](https://docs.microsoft.com/visualstudio/modeling/the-dsltexttransform-command)。  
  
DslTextTransform.cmd 是一个脚本调用 TextTransform.exe 和运行使用常用的选项。 可以使用 DslTextTransformation.cmd 来自动执行的每夜生成您[!INCLUDE[dsl](../includes/dsl-md.md)]项目。 有关详细信息，请参阅[使用 TextTransform 实用工具生成文件](../modeling/generating-files-with-the-texttransform-utility.md)。  
  
 DslTextTransform.cmd 位于以下目录中：  
  
 **\<Visual Studio SDK 安装路径 > \VisualStudioIntegration\Tools\Bin**  
  
 作为输入 DslTextTransform.cmd，可以指定以下参数：  
  
-   域模型项目的输出目录。  
  
-   设计器定义项目的输出目录。  
  
-   文本模板文件的位置。  
  
 DslTextTransform.cmd 处理指定的文本模板文件使用默认指令处理器和程序集。 如果创建自定义指令处理器，您可以创建自己调用 TextTransform.exe 的批处理文件。 在此批处理文件中，可以指定您的程序集和关联的自定义指令处理器。



