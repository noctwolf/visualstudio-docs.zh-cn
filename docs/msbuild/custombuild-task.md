---
title: CustomBuild 任务 | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.custombuild
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), CustomBuild task
- CustomBuild task (MSBuild (Visual C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 6d466dec85a0bdf242120ef5e88a0d5f5d2ac48e
ms.sourcegitcommit: 0ef51e3517436a85cfb85bf492722d566ce602c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934518"
---
# <a name="custombuild-task"></a>CustomBuild 任务

包装 Visual C++ 编译器工具 cmd.exe。 此类派生自 [TrackedVCToolTask](../msbuild/trackedvctooltask-base-class.md)，但不使用文件跟踪来发现文件依赖项。 所有依赖项都应显式指定为 AdditionalDependencies，以便使增量生成正常工作。


## <a name="parameters"></a>参数

下表描述了 CustomBuild 任务的参数。

|参数|说明|
|---------------|-----------------|
|**BuildSuffix**|可选的 string 参数。|
|**Sources**|必需的 **ITaskItem[]** 参数。|
|**TrackerLogDirectory**|可选的 string 参数。|

## <a name="see-also"></a>请参阅

[任务参考](../msbuild/msbuild-task-reference.md)
