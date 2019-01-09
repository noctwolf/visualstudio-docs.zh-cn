---
title: 设置当前进程
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0c01c399dc76d1b328443edef27edd9a921b1b9c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53855278"
---
# <a name="set-current-process"></a>设置当前进程
将指定的进程设置为调试器中的活动进程。

## <a name="syntax"></a>语法

```cmd
Debug.SetCurrentProcess index
```

## <a name="arguments"></a>自变量
 `index`

 必需。 进程的索引。

## <a name="remarks"></a>备注
 调试时可以附加到多个进程，但在任何给定时间，调试器中只有一个进程处于活动状态。 可以使用 `SetCurrentProcess` 命令设置活动进程。

## <a name="example"></a>示例

```cmd
>Debug.SetCurrentProcess 1
```

## <a name="see-also"></a>请参阅

- [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)
- [“命令”窗口](../../ide/reference/command-window.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)