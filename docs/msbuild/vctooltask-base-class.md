---
title: VCToolTask 类 | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 4c7cc3490735dbd9ac43cd43555ec673cc3afccd
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070392"
---
# <a name="vctooltask-base-class"></a>VCToolTask 基类

许多任务最终继承自 <xref:Microsoft.Build.Utilities.Task> 类和 [ToolTask](/dotnet/api/microsoft.build.utilities.tooltask) 类。 此类向派生自该类的任务添加几个参数。 本文档中列出了这些参数。

## <a name="parameters"></a>参数

下表介绍了 VCToolTask 基类的参数。

|参数|说明|
|---------------|-----------------|
|**ActiveToolSwitchesValues**|可选的 Dictionary\<string, ToolSwitch> 参数。|
|**AdditionalOptions**|可选的 string 参数。|
|**EffectiveWorkingDirectory**|可选的 string 参数。|
|**EnableErrorListRegex**|可选的 bool 参数。<br/><br/>默认值为 `true`。|
|**ErrorListRegex**|可选的 **ITaskItem[]** 参数。|
|**ErrorListListExclusion**|可选的 **ITaskItem[]** 参数。|
|**GenerateCommandLine**|可选的 string 参数。<br/><br/>使用 CommandLineFormat format [default = CommandLineFormat.ForBuildLog] 和 EscapeFormat escapeFormat [default = EscapeFormat.Default] 值。|
|**GenerateCommandLineExceptSwitches**|可选的 string 参数。<br/><br/>使用 string[] switchesToRemove、CommandLineFormat format [default = CommandLineFormat.ForBuildLog] 和 EscapeFormat escapeFormat [default = EscapeFormat.Default] 值。|

## <a name="see-also"></a>请参阅

[任务参考](../msbuild/msbuild-task-reference.md)<br/>
[任务](../msbuild/msbuild-tasks.md)