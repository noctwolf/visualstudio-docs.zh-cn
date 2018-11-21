---
title: devenv.exe setup 开关
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: eca577c0e4646821262c953cf48256937eed386c
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948369"
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)

/Setup 开关使 Visual Studio 合并所有可用的 Vspackage 中描述菜单、工具栏和命令组的资源元数据。

## <a name="syntax"></a>语法

```shell
devenv /setup
```

## <a name="remarks"></a>备注

此开关不带参数。 `devenv /setup` 命令通常作为安装过程的最后一步给出。 使用 `/setup` 开关不会启动 Visual Studio。

> [!NOTE]
> 必须以管理员身份运行 `devenv` 才能使用 `/setup` 开关。

## <a name="example"></a>示例

此示例展示包含 Vspackage 的 Visual Studio 版本安装的最后一步。

```shell
devenv /setup
```

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)