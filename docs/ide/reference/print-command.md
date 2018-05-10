---
title: Print 命令
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ef4f0c5c6bd5be2820e1f666529fc43fac59763
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="print-command"></a>Print 命令
计算表达式或显示指定文本。

## <a name="syntax"></a>语法

```cmd
Debug.Print text
```

## <a name="arguments"></a>自变量
 `text`

 必须的。 要计算的表达式或要显示的文本。

## <a name="remarks"></a>备注
 可使用问号 (?) 作为此命令的别名。 例如，命令

```cmd
>Debug.Print expA
```

 也可写作

```cmd
>? expA
```

 此命令的这两个版本都将返回表达式 `expA` 的当前值。

## <a name="example"></a>示例

```cmd
>Debug.Print varA
```

## <a name="see-also"></a>请参阅

- [“计算语句”命令](../../ide/reference/evaluate-statement-command.md)
- [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)
- [“命令”窗口](../../ide/reference/command-window.md)
- [“查找/命令”框](../../ide/find-command-box.md)
- [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)