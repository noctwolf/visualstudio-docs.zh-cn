---
title: ParallelCustomBuild 任务 | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.parallelcustombuild
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), ParallelCustomBuild task
- ParallelCustomBuild task (MSBuild (Visual C++))
author: mikeblome
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 506ead6680bd9a0aaaf38d6959da02a14dfee337
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070355"
---
# <a name="parallelcustombuild-task"></a>ParallelCustomBuild 任务

运行 [CustomBuild 任务](../msbuild/custombuild-task.md)的并行实例。

## <a name="parameters"></a>参数

下表介绍了 ParallelCustomBuild 任务的参数。

|参数|说明|
|---------------|-----------------|
|**BreakOnFirstFailure**|可选的 bool 参数。|
|**MaxItemsInBatch**|可选 **int** 参数。|
|**MaxProcesses**|可选 **int** 参数。|
|**Sources**|必需的 **ITaskItem[]** 参数。|

## <a name="see-also"></a>请参阅

[任务参考](../msbuild/msbuild-task-reference.md)