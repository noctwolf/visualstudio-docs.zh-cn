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
ms.openlocfilehash: 0f3d78ebb63434df38735bdf24e9d4fcba8f172c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
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