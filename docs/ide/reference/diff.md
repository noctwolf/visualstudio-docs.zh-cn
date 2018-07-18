---
title: -Diff
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6cbf0f8f9fa2e97908e2ae13e3961382a7250a91
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704910"
---
# <a name="diff"></a>/Diff
比较两个文件。 差异将在特殊 Visual Studio 窗口中显示。

## <a name="syntax"></a>语法

```cmd
devenv /Diff SourceFile, TargetFile, [SourceDisplayName],[TargetDisplayName]
```

## <a name="arguments"></a>自变量
 `SourceFile`

 必须的。 要比较的第一个文件的完整路径和名称。

 `TargetFile`

 必须的。 要比较的第二个文件的完整路径和名称

 `SourceDisplayName`

 可选。 第一个文件的显示名称。

 `TargetDisplayName`

 可选。 第二个文件的显示名称。