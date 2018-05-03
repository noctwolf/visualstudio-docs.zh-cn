---
title: “计算语句”命令
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0c2ec882bb2fdc9d0f3b74a0552c85a7b286617c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="evaluate-statement-command"></a>“计算语句”命令
计算并显示给定的语句。

## <a name="syntax"></a>语法

```
Debug.EvaluateStatement text
```

## <a name="arguments"></a>自变量
 `text`（必需）。 要评估的语句。

## <a name="remarks"></a>备注
 用于输入 EvaluateStatement 命令的窗口确定是将等号 (=) 解释为比较运算符还是赋值运算符。

 在“命令”窗口中，将等号 (=) 解释为比较运算符。 例如，如果变量 `a` 和 `b` 的值不同，则命令

```
>Debug.EvaluateStatement(a=b)
```

 将返回 `false` 的值。

 与此相反，在“即时”窗口中，将等号 (=) 解释为赋值运算符。 例如，命令

```
>Debug.EvaluateStatement(a=b)
```

 将为变量 `a` 赋予变量 `b` 的值。

## <a name="example"></a>示例

```
>Debug.EvaluateStatement(a+b)
```

## <a name="see-also"></a>请参阅

- [“打印”命令](../../ide/reference/print-command.md)
- [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)
- [“命令”窗口](../../ide/reference/command-window.md)
- [“查找/命令”框](../../ide/find-command-box.md)
- [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)