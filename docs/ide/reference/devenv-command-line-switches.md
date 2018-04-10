---
title: Visual Studio devenv 命令行开关 | Microsoft Docs
ms.date: 02/28/2018
ms.technology: vs-ide-general
ms.topic: article
helpviewer_keywords:
- switches, Devenv
- command-line switches, Devenv
- command line [Visual Studio], switches
- Devenv
ms.assetid: e12bc6ed-74fd-4bea-8d7c-89b99c20bad8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b507ff8710e3257f2da61a32baa81a18441c3aff
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
# <a name="devenv-command-line-switches"></a>Devenv 命令行开关

Devenv 可用来设置集成开发环境 (IDE) 的各个选项，以及从命令行生成、调试和部署项目。 使用这些开关从脚本或 .bat 文件（例如每夜生成的脚本）运行 IDE，或以特定配置启动 IDE。

> [!NOTE]
> 对于与生成相关的任务，推荐使用 MSBuild，而非 devenv。 有关详细信息，请参阅 [MSBuild 命令行参考](../../msbuild/msbuild-command-line-reference.md)。

## <a name="devenv-switch-syntax"></a>Devenv 开关语法

默认情况下，devenv 命令将开关传递给 devenv.com 实用工具。 Devenv.com 实用工具通过标准系统流提供输出，如 `stdout` 和 `stderr`。 该实用工具在捕获输出时（例如输出到 .txt 文件）确定相应的 I/O 重定向。

另一方面，以 `devenv.exe` 开头的命令可以使用相同的开关，但会绕过 devenv.com 实用工具。

`devenv` 开关的语法规则与其他 DOS 命令行实用工具类似。 下列语法规则适用于所有 `devenv` 开关及其参数：

- 命令以 `devenv` 开头。

- 开关不区分大小写。

- 指定一个解决方案或项目时，第一个参数是解决方案文件或项目文件的名称，包括文件路径。

- 如果第一个参数是一个非解决方案或项目的文件，在适当的编辑器中的 IDE 新实例中打开该文件。

- 如果提供项目文件名而不是解决方案文件名，`devenv` 命令会在项目文件的父文件夹中搜索具有相同名称的解决方案文件。 例如，`devenv /build myproject1.vbproj` 命令在父文件夹中搜索命名为“myproject1.sln”的解决方案文件。

    > [!NOTE]
    > 引用此项目的唯一一个解决方案文件应位于其父文件夹中。 如果父文件夹不包含引用此项目的解决方案文件，或父文件夹包含引用此项目的两个或更多解决方案文件，将创建一个临时解决方案文件。

- 当文件路径和文件名中包含空格时，必须用引号 ("") 将它们括起来。 例如 "c:\project a\\"。

- 在同一行上的开关和参数之间插入一个空白字符。 例如，**devenv /log output.txt** 命令将打开 IDE，并将该会话的所有日志信息输出到 output.txt。

- 您无法在 `devenv` 命令中使用模式匹配语法。

## <a name="devenv-switches"></a>Devenv 开关

下列命令行开关显示 IDE 并执行描述的任务。

|命令行开关|描述|
|-------------------------|-----------------|
|[/Command](../../ide/reference/command-devenv-exe.md)|启动 IDE 并执行指定的命令。|
|[/DebugExe](../../ide/reference/debugexe-devenv-exe.md)|在调试器的控制下加载 C++ 可执行文件。 此开关不可用于 Visual Basic 或 C# 可执行文件。 有关详细信息，请参阅[自动启动调试器中的进程](../../debugger/debug-multiple-processes.md#BKMK_Automatically_start_an_process_in_the_debugger)。|
|[/LCID 或 /l](../../ide/reference/lcid-devenv-exe.md)|为 IDE 设置默认语言。 如果 Visual Studio 的安装中不包括指定的语言，将忽略此设置。|
|[/Log](../../ide/reference/log-devenv-exe.md)|启动 Visual Studio 并将所有活动记录到日志文件中。|
|[/Run 或 /r](../../ide/reference/run-devenv-exe.md)|编译并运行指定的解决方案。|
|[/Runexit](../../ide/reference/runexit-devenv-exe.md)|编译并运行指定的解决方案，在运行该解决方案时最小化 IDE，并在解决方案完成运行后关闭 IDE。|
|[/UseEnv](../../ide/reference/useenv-devenv-exe.md)|使 IDE 使用 PATH、INCLUDE 和 LIB 环境变量进行 C++ 编译，而不是使用“选项”对话框中“项目”选项的“VC++ 目录”节中指定的设置。 此开关与使用 C++ 的桌面开发工作负载一起安装。 有关更多信息，请参阅 [为命令行生成设置路径和环境变量](/cpp/build/setting-the-path-and-environment-variables-for-command-line-builds)。|
|[/Edit](../../ide/reference/edit-devenv-exe.md)|在此应用程序的运行实例中打开指定的文件。 如果没有正在运行的实例，它启动具有简化的窗口布局的新实例。|
|[/SafeMode](../../ide/reference/safemode-devenv-exe.md)|以安全模式启动 Visual Studio，并仅加载默认的环境和服务以及第三方包的发布版。|
|[/ResetSkipPkgs](../../ide/reference/resetskippkgs-devenv-exe.md)|清除用户因希望避免加载有问题的 VSPackage 而添加到 VSPackage 中的所有 SkipLoading 标记。|
|[/Setup](../../ide/reference/setup-devenv-exe.md)|强制 Visual Studio 合并所有可用的 VSPackage 中描述菜单、工具栏和命令组的资源元数据。 必须以管理员身份运行此命令。|

以下命令行开关不显示 IDE。

|命令行开关|描述|
|-------------------------|-----------------|
|[/?](../../ide/reference/q-devenv-exe.md)|在“命令提示符”窗口中显示 devenv 开关的相关帮助信息。<br /><br /> **Devenv /?**|
|[build](../../ide/reference/build-devenv-exe.md)|根据指定解决方案的配置，生成指定的解决方案或项目。<br /><br /> **Devenv myproj.csproj /build**|
|[/Clean](../../ide/reference/clean-devenv-exe.md)|删除由生成命令创建的任何文件，而不影响源文件。<br /><br /> **Devenv myproj.csproj /clean**|
|[/Deploy](../../ide/reference/deploy-devenv-exe.md)|根据解决方案配置生成解决方案以及部署所需的文件。<br /><br /> **Devenv myproj.csproj /deploy**|
|[/Diff](../../ide/reference/diff.md)|比较两个文件。 采用四个参数：SourceFile、TargetFile、SourceDisplayName(optional)、TargetDisplayName(optional)。|
|[/Out](../../ide/reference/out-devenv-exe.md)|用于在生成时指定一个文件来接收错误。<br /><br /> **Devenv myproj.csproj /build /out log.txt**|
|[/Project](../../ide/reference/project-devenv-exe.md)|要生成、清理或部署的项目。 仅当已提供 /build、/rebuild、/clean 或 /deploy 开关之后，才可使用此开关。|
|[/ProjectConfig](../../ide/reference/projectconfig-devenv-exe.md)|指定要生成或部署的项目配置。 仅当已提供 /project 开关之后，才可使用此开关。|
|[/Rebuild](../../ide/reference/rebuild-devenv-exe.md)|根据指定解决方案的配置，清理并生成指定的解决方案或项目。|
|[/ResetSettings](../../ide/reference/resetsettings-devenv-exe.md)|还原 Visual Studio 默认设置。 可以选择将这些设置重置为指定的 .vssettings 文件。|
|[/Upgrade](../../ide/reference/upgrade-devenv-exe.md)|将指定的解决方案文件及其所有项目文件或指定的项目文件升级为这些文件的当前 Visual Studio 格式。|

## <a name="see-also"></a>请参阅

* [“选项”对话框 ->“环境”->“常规”](../../ide/reference/general-environment-options-dialog-box.md)