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
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 183cdefbca29db486b84cb61f90501507e298838
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070357"
---
# <a name="custombuild-task"></a>CustomBuild 任务

包装 Visual C++ 编译器工具 cmd.exe。

## <a name="parameters"></a>参数

下表描述了 CustomBuild 任务的参数。

|参数|说明|
|---------------|-----------------|
|**BuildSuffix**|可选的 string 参数。|
|**Sources**|必需的 **ITaskItem[]** 参数。|
|**TrackerLogDirectory**|可选的 string 参数。|

## <a name="see-also"></a>请参阅

[任务参考](../msbuild/msbuild-task-reference.md)