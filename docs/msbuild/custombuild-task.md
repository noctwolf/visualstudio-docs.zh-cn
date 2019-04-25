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
ms.openlocfilehash: 197128fadb660ab06686d13ec304a5d9d1698070
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778132"
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