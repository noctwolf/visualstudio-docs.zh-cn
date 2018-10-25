---
title: DevEnv Build 开关
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- builds, command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
- command-line builds
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cdd510e523aaabc468c1f01626593e51d0ad1558
ms.sourcegitcommit: 9571742f4a808c75b1034aa72fc24b54bc50692e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410957"
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)

使用指定解决方案配置文件生成解决方案。

## <a name="syntax"></a>语法

```cmd
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]
```

## <a name="arguments"></a>自变量

|||
|-|-|
|*SolutionName*|必须的。 解决方案文件的完整路径和名称。|
|*SolnConfigName*|必须的。 用于生成在 SolutionName 中命名的解决方案的解决方案配置的名称。 如果有多个可用的解决方案平台，还必须指定平台，例如“调试 \|Win32”。|
|/project ProjName|可选。 解决方案中项目文件的路径和名称。 可以输入从 SolutionName 文件夹到项目文件的相对路径、项目的显示名称或项目文件的完整路径和名称。|
|/projectconfig ProjConfigName|可选。 在生成命名的项目时要使用的项目生成配置的名称。 如果有多个可用的项目平台，还必须指定平台，例如“调试 \|Win32”。|

## <a name="remarks"></a>备注

- 在集成开发环境 (IDE) 中，/build 开关具有与“生成解决方案”菜单命令相同的功能。

- 用双引号将含有空格的字符串引起来。

- “命令”窗口或使用 /out 开关指定的任何日志文件中都可显示生成的摘要信息（包括错误）。

- /build 命令仅生成自上次生成后发生变化的项目。 若要生成解决方案中的所有项目，请改用 [/rebuild](../../ide/reference/rebuild-devenv-exe.md)。

- 如果收到一条错误消息：“无效的项目配置”，请确保已指定解决方案平台或项目平台（例如“调试\|Win32”）。

## <a name="example"></a>示例

以下命令生成项目“CSharpConsoleApp”，在“MySolution”的“调试”解决方案配置中采用“调试”项目生成配置。

```cmd
devenv "C:\Visual Studio Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>请参阅

- [生成并清理项目和解决方案](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)