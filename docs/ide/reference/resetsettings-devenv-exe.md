---
title: -ResetSettings (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3c3d3a6ef558b510cfde716716daf97a549fbba4
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33703982"
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)

还原 Visual Studio 的默认设置，自动启动 Visual Studio IDE。 可选择将这些设置重置为指定的 vssettings 文件。

默认设置由首次启动 Visual Studio 时选择的配置文件决定。

## <a name="syntax"></a>语法

```cmd
Devenv /ResetSettings SettingsFile
```

## <a name="arguments"></a>自变量

`SettingsFile`

vssettings 文件的完整路径和名称应用于 Visual Studio。

若要还原常规开发设置配置文件，请使用 `General`。

## <a name="remarks"></a>备注

如果未指定任何 `SettingsFile`，在下次启动 Visual Studio 时，系统将提示选择默认的设置集合。

## <a name="example"></a>示例

下面的命令行应用 `MySettings.vssettings` 文件中存储的设置。

```cmd
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"
```

## <a name="see-also"></a>请参阅

- [个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)
- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)