---
title: -Log (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93d3e4323638d40f003247a2c5bd35c812cc1c69
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
将所有活动记录到日志文件以用于疑难解答。 此文件在你至少调用一次 `devenv /log` 后显示。 默认情况下，日志文件为：

 %APPDATA%\Microsoft\VisualStudio\\Version\ActivityLog.xml

 其中，“版本”是 Visual Studio 的版本。 但是，可以指定一个不同的路径和文件名。

## <a name="syntax"></a>语法

```
Devenv /log Path\NameOfLogFile
```

## <a name="remarks"></a>备注
 此开关必须显示在命令行的结尾，位于所有其他开关之后。

 对于你使用 /log 开关调用的所有 Visual Studio 实例，都会记录日志。 对于不使用此开关调用的 Visual Studio 实例，将不记录日志。

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)