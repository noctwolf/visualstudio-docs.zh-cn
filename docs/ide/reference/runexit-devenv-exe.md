---
title: -Runexit (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- runexit Devenv switch
- Devenv, /runexit switch
- /runexit Devenv switch
ms.assetid: bfc94875-5fc0-4110-b961-d59c0b403790
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dff2f028c94013df4f69e9aca244f98c307d2782
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948226"
---
# <a name="runexit-devenvexe"></a>/Runexit (devenv.exe)
编译和运行指定的项目或解决方案，然后关闭集成开发环境 (IDE)。

## <a name="syntax"></a>语法

```
devenv /runexit {SolutionName|ProjectName}
```

## <a name="arguments"></a>自变量
 `SolutionName`

 必须的。 解决方案文件的完整路径和名称。

 `ProjectName`

 必须的。 项目文件的完整路径和名称。

## <a name="remarks"></a>备注
 根据为活动解决方案配置指定的设置编译并运行指定项目或解决方案。 此开关会在项目或解决方案处于运行状态时最小化 IDE，会在项目或解决方案完成运行后关闭 IDE。

-   用双引号将含有空格的字符串引起来。

-   “命令”窗口或使用 `/out` 开关指定的任何日志文件中都可显示摘要信息（包括错误）。

## <a name="example"></a>示例
 此示例会在最小化的 IDE 中使用活动部署配置运行解决方案 `MySolution`，然后关闭 IDE。

```
devenv /runexit "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"
```

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)
- [/Run (devenv.exe)](../../ide/reference/run-devenv-exe.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)