---
title: GetOutputFileName 任务 | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.getoutputfilename
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), GetOutputFileName task
- GetOutputFileName task (MSBuild (Visual C++))
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: ee44e891c8c5f6a95971cade0536b2a5ec5b4688
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070363"
---
# <a name="getoutputfilename-task"></a>GetOutputFileName 任务

用于获取有关 cl 和其他工具（只允许指定输出目录或完整文件名或不允许指定任何内容）的输出文件名的帮助程序任务。

## <a name="parameters"></a>参数

下表显示 GetOutputFileName 任务的参数。

|参数|说明|
|---------------|-----------------|
|**OutputExtension**|必需的 **String** 参数。|
|**OutputFile**|可选的 string 输出参数。|
|**OutputPath**|可选的 string 参数。|
|SourceFile|必需的 **String** 参数。|

## <a name="see-also"></a>请参阅

[任务参考](../msbuild/msbuild-task-reference.md)