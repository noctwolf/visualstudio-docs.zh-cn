---
title: -DebugExe (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
- debugging executables
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a93a582af62ed0eac8cdc0f5da55ac7bda555152
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55008967"
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)

打开要调试的指定可执行文件。

## <a name="syntax"></a>语法

```shell
devenv /DebugExe ExecutableFile
```

## <a name="arguments"></a>自变量

- ExecutableFile

  必需。 `.exe` 文件的路径和文件名。 如果 `.exe` 文件找不到或不存在，Visual Studio 不会显示任何警告或错误，而是正常启动。

## <a name="remarks"></a>备注

ExecutableFile 参数后跟的任何字符串都作为参数传递到相应文件。

## <a name="example"></a>示例

以下示例打开文件 `MyApplication.exe` 进行调试。

```shell
devenv /debugexe MyApplication.exe
```

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)