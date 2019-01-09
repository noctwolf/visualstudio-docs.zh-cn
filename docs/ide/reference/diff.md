---
title: -Diff
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf58c25611fd52c6e8db8e8210101e1c80153275
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53844533"
---
# <a name="diff"></a>/Diff
比较两个文件。 差异将在特殊 Visual Studio 窗口中显示。

## <a name="syntax"></a>语法

```cmd
devenv /Diff SourceFile, TargetFile, [SourceDisplayName],[TargetDisplayName]
```

## <a name="arguments"></a>自变量
 `SourceFile`

 必需。 要比较的第一个文件的完整路径和名称。

 `TargetFile`

 必需。 要比较的第二个文件的完整路径和名称

 `SourceDisplayName`

 可选。 第一个文件的显示名称。

 `TargetDisplayName`

 可选。 第二个文件的显示名称。