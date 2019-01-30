---
title: “切换断点”命令
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- debug.togglebreakpoint
helpviewer_keywords:
- ToggleBreakpoint command
- Debug.ToggleBreakPoint command
- Toggle Breakpoint command
ms.assetid: d50dfadb-ce79-4d5e-9c09-1cfddd57876d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 71fc920451848558ddc6b04b5940787926e245c0
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54930077"
---
# <a name="toggle-breakpoint-command"></a>“切换断点”命令
在文件中的当前位置，根据其当前状态打开或关闭断点。

## <a name="syntax"></a>语法

```
Debug.ToggleBreakpoint [text]
```

## <a name="arguments"></a>自变量
 `text`（可选）。 如果已指定文本，该行将标记为已命名断点。 否则，该行标记为未命名断点，其结果与按下 F9 时的效果类似。

## <a name="example"></a>示例
 以下示例切换当前断点。

```
>Debug.ToggleBreakpoint
```

## <a name="see-also"></a>请参阅

- [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)
- [“命令”窗口](../../ide/reference/command-window.md)
- [“查找/命令”框](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)