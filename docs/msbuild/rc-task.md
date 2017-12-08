---
title: "RC 任务 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- vc.task.rc
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- RC task (MSBuild (Visual C++))
- MSBuild (Visual C++), RC task
ms.assetid: 2fd26c75-a056-4dda-9f7e-2f90d3748d88
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 73e4544ab00142929bbd8d8dbdb154355c48c609
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="rc-task"></a>RC 任务
包装 Microsoft Windows 资源编译器工具 rc.exe。 RC 任务将游标、图标、位图、对话框和字体等资源编译为一个资源 (.res) 文件。 有关详细信息，请参阅 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 网站上的“资源编译器”。  
  
## <a name="parameters"></a>参数  
 下表描述了 RC 任务的参数。 大多数任务参数和若干组参数都对应于命令行选项。  
  
|参数|描述|  
|---------------|-----------------|  
|**AdditionalIncludeDirectories**|可选 **String []** 参数。<br /><br /> 将目录添加到在其中搜索包含文件的目录列表中。<br /><br /> 有关详细信息，请参阅 MSDN 网站上 [Using RC (The RC Command Line)](http://go.microsoft.com/fwlink/?LinkId=155730)（使用 RC（RC 命令行））中的 /I 选项。|  
|**AdditionalOptions**|可选 **String** 参数。<br /><br /> 命令行 optionsor 的列表示例，“/option1 /option2 /option#”。 使用此参数可指定未由任何其他 RC 任务参数表示的命令行选项。<br /><br /> 有关详细信息，请参阅 MSDN 网站上 [Using RC (The RC Command Line)](http://go.microsoft.com/fwlink/?LinkId=155730)（使用 RC（RC 命令行））中的选项。|  
|**区域性**|可选 **String** 参数。<br /><br /> 指定表示资源中使用的区域性的区域设置 ID。<br /><br /> 有关详细信息，请参阅 MSDN 网站上 [Using RC (The RC Command Line)](http://go.microsoft.com/fwlink/?LinkId=155730)（使用 RC（RC 命令行））中的 /l 选项。|  
|**IgnoreStandardIncludePath**|可选 **Boolean** 参数。<br /><br /> 如果为 `true`，则阻止资源编译器在搜索头文件或资源文件时检查 INCLUDE 环境变量。<br /><br /> 有关详细信息，请参阅 MSDN 网站上 [Using RC (The RC Command Line)](http://go.microsoft.com/fwlink/?LinkId=155730)（使用 RC（RC 命令行））中的 /x 选项。|  
|**NullTerminateStrings**|可选 **Boolean** 参数。<br /><br /> 如果为 `true`，则以 null 终止字符串表中的所有字符串。<br /><br /> 有关详细信息，请参阅 MSDN 网站上 [Using RC (The RC Command Line)](http://go.microsoft.com/fwlink/?LinkId=155730)（使用 RC（RC 命令行））中的 /n 选项。|  
|**PreprocessorDefinitions**|可选 **String []** 参数。<br /><br /> 定义资源编译器的一个或多个预处理器符号。 指定宏符号的列表。<br /><br /> 有关详细信息，请参阅 MSDN 网站上 [Using RC (The RC Command Line)](http://go.microsoft.com/fwlink/?LinkId=155730)（使用 RC（RC 命令行））中的 /d 选项。 另请参阅此表中的 UndefinePreprocessorDefinitions。|  
|**ResourceOutputFileName**|可选 **String** 参数。<br /><br /> 指定资源文件的名称。 指定资源文件名称。<br /><br /> 有关详细信息，请参阅 MSDN 网站上 [Using RC (The RC Command Line)](http://go.microsoft.com/fwlink/?LinkId=155730)（使用 RC（RC 命令行））中的 /fo 选项。|  
|**ShowProgress**|可选 **Boolean** 参数。<br /><br /> 如果为 `true`，则显示报告编译器进度的消息。<br /><br /> 有关详细信息，请参阅 MSDN 网站上 [Using RC (The RC Command Line)](http://go.microsoft.com/fwlink/?LinkId=155730)（使用 RC（RC 命令行））中的 /v 选项。|  
|**源**|必选 `ITaskItem[]` 参数。<br /><br /> 定义可以被任务使用和发出的 MSBuild 源文件项的数组。|  
|**SuppressStartupBanner**|可选 **Boolean** 参数。<br /><br /> 如果为 `true`，则在任务开始时阻止显示版权和版本号消息。<br /><br /> 有关详细信息，请键入 /? 命令行选项，然后查看 /nologo 选项。|  
|**TrackerLogDirectory**|可选 **String** 参数。<br /><br /> 指定跟踪器日志目录。|  
|**UndefinePreprocessorDefinitions**|取消定义预处理器符号。<br /><br /> 有关详细信息，请参阅 MSDN 网站上 [Using RC (The RC Command Line)](http://go.microsoft.com/fwlink/?LinkId=155730)（使用 RC（RC 命令行））中的 /u 选项。 另请参阅此表中的 PreprocessorDefinitions。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>另请参阅  
 [任务参考](../msbuild/msbuild-task-reference.md)