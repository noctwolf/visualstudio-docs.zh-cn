---
title: -UseEnv (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VC.Project.UseEnvVars.ExcludePath
- VC.Project.UseEnvVars.LibraryPath
- VC.Project.UseEnvVars.SourcePath
- VC.Project.UseEnvVars.Include
- VC.Project.UseEnvVars.Path
- VC.Project.UseEnvVars.ReferencePath
helpviewer_keywords:
- UseEnv switch
- /UseEnv Devenv switch
- Devenv, /UseEnv
ms.assetid: 2dd14603-a61b-42d2-ba31-427a0ee8a799
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5fd76e44b2e503bd7b444e83bb9a64abceeaa561
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="useenv-devenvexe"></a>/UseEnv (devenv.exe)

启动 Visual Studio，并将环境变量加载到“VC++ 目录”对话框中。

> [!NOTE]
> 此开关与使用 C++ 的桌面开发工作负载一起安装。

## <a name="syntax"></a>语法

```shell
Devenv /useenv
```

## <a name="example"></a>示例

以下示例启动 Visual Studio，并将环境变量加载到“VC++ 目录”对话框中。

```shell
Devenv.exe /useenv
```

## <a name="see-also"></a>请参阅

* [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)