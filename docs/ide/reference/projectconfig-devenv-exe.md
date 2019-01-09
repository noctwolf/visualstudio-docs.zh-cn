---
title: DevEnv ProjectConfig 开关
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- /projectconfig Devenv switch
- configurations, rebuilding
- deployment projects, creating
- configurations, cleaning
- deployment projects, specifying
- deployment projects, adding
- build configurations, specifying
- Devenv, /projectconfig switch
- projectconfig Devenv switch (/projectconfig)
- projects [Visual Studio], build configuration
- projects [Visual Studio], cleaning
ms.assetid: 6b54ef59-ffed-4f62-a645-1279ede97ebf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7ca481d23757cc9022042db42a6d4be477880367
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53967912"
---
# <a name="projectconfig-devenvexe"></a>/ProjectConfig (devenv.exe)

指定生成、清理、重新生成或部署 /project 参数中命名的项目时要应用的项目生成配置。

## <a name="syntax"></a>语法

```cmd
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]
```

## <a name="arguments"></a>自变量

|||
|-|-|
|/build|生成 /project 参数所指定的项目。|
|/clean|清理在生成过程中创建的所有中间文件和输出目录。|
|/rebuild|清理然后生成 /project 参数所指定的项目。|
|/deploy|指定生成或重新生成后部署该项目。|
|*SolnConfigName*|必需。 将应用于 SolutionName 中命名的解决方案的解决方案配置的名称。 如果有多个可用的解决方案平台，还必须指定平台，例如“调试 \|Win32”。|
|*SolutionName*|必需。 解决方案文件的完整路径和名称。|
|/project ProjName|可选。 解决方案中项目文件的路径和名称。 可以输入从 SolutionName 文件夹到项目文件的相对路径、项目的显示名称或项目文件的完整路径和名称。|
|/projectconfig ProjConfigName|可选。 要应用于 /project 参数所指定项目的项目生成配置的名称。 如果有多个可用的解决方案平台，还必须指定平台，例如“调试 \|Win32”。|

## <a name="remarks"></a>备注

/projectconfig 开关必须和 /project 开关一起用作 /build、/clean、/rebuild 或 /deploy 命令的一部分。

用双引号将含有空格的字符串引起来。

“命令”窗口或使用 /out 开关指定的任何日志文件中都可显示生成的摘要信息（包括错误）。

## <a name="example"></a>示例

以下命令生成项目“CSharpConsoleApp”，在“MySolution”的“调试”解决方案配置中采用“调试”项目生成配置：

```cmd
devenv "C:\Visual Studio Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)
- [/Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Deploy (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)