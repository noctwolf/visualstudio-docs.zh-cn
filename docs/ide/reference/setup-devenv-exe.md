---
title: "devenv.exe 安装程序开关 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93f03de74540d130d66ce123b355691e0828b93e
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2018
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)

/Setup 开关使 Visual Studio 合并所有可用的 Vspackage 中描述菜单、工具栏和命令组的资源元数据。

## <a name="syntax"></a>语法

```
devenv /setup
```

## <a name="remarks"></a>备注

此开关不带参数。 `devenv /setup` 命令通常作为安装过程的最后一步给出。 使用 `/setup` 开关不会启动 Visual Studio。

必须以管理员身份运行 `devenv` 才能使用 [/setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) 和 [/InstallVSTemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) 开关。

## <a name="example"></a>示例

此示例展示包含 Vspackage 的 Visual Studio 版本安装的最后一步。

```
devenv /setup
```

## <a name="see-also"></a>请参阅

[Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)