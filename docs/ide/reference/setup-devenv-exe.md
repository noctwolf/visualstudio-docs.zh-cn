---
title: "devenv.exe 安装程序开关 | Microsoft Docs"
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e37fe50eefc36e7b5396f396d2b614851a0bd9cb
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
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

[Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)