---
title: “设置当前线程”命令
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- debug.setcurrentthread
helpviewer_keywords:
- Set Current Thread command
- Debug.SetCurrentThread command
ms.assetid: 9917ed1d-6c30-4d94-b2f0-69acce74f1b2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 03d253d9be0d8bf5456f1a436d45762d6f030f86
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53855333"
---
# <a name="set-current-thread-command"></a>“设置当前线程”命令
将指定的线程设置为当前线程。

## <a name="syntax"></a>语法

```
Debug.SetCurrentThread index
```

## <a name="arguments"></a>自变量
 `index`

 必需。 按线程的索引选择线程。

## <a name="example"></a>示例

```
>Debug.SetCurrentThread 1
```

## <a name="see-also"></a>请参阅

- [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)
- [“命令”窗口](../../ide/reference/command-window.md)
- [“查找/命令”框](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)