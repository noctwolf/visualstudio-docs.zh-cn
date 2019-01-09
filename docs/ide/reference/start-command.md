---
title: “启动”命令
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f3e15e9bcea439e6e01ff3bb233622d119fa4b46
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53903924"
---
# <a name="start-command"></a>“启动”命令
开始调试启动项目。

## <a name="syntax"></a>语法

```cmd
Debug.Start [address]
```

## <a name="arguments"></a>自变量
 `address`

 可选。 程序挂起执行的地址，类似于源代码中的断点。 此参数仅在调试模式下有效。

## <a name="remarks"></a>备注
 “启动”命令在执行时会对指定的地址执行 RunToCursor 操作。

## <a name="example"></a>示例
 此示例启动调试器并忽略任何发生的异常。

```cmd
>Debug.Start
```

## <a name="see-also"></a>请参阅

- [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)
- [“命令”窗口](../../ide/reference/command-window.md)
- [“查找/命令”框](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)