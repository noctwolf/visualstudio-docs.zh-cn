---
title: -Run (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /run Devenv
- run Devenv switch
- applications [Visual Studio], running
- /r Devenv switch
- Devenv, /run switch
- r Devenv switch (/r)
ms.assetid: b1f22f9d-39a5-4918-8a2a-4b5c1e872665
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9e10b12729ed8f547c2658c0f4ce6ece84a12dbe
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="run-devenvexe"></a>/Run (devenv.exe)
编译并运行指定的项目或解决方案。

## <a name="syntax"></a>语法

```cmd
devenv {/run|/r} {SolutionName|ProjectName}
```

## <a name="arguments"></a>自变量
 `SolutionName`

 必须的。 解决方案文件的完整路径和名称。

 `ProjectName`

 必须的。 项目文件的完整路径和名称。

## <a name="remarks"></a>备注
 根据为活动解决方案配置指定的设置编译并运行指定项目或解决方案。 此开关启动集成开发环境 (IDE) ，并在项目或解决方案已完成运行后让该环境保持活动状态。

-   用双引号将含有空格的字符串引起来。

-   “命令”窗口或使用 `/out` 开关指定的任何日志文件中都可显示摘要信息（包括错误）。

## <a name="example"></a>示例
 该示例使用活动部署配置运行解决方案 `MySolution`。

```cmd
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"
```

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)
- [/Runexit (devenv.exe)](../../ide/reference/runexit-devenv-exe.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)