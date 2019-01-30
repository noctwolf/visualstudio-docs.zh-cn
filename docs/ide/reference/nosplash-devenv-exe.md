---
title: -NoSplash (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /NoSplash switch
- /NoSplash Devenv switch
- NoSplash Devenv switch
author: DennisLee-DennisLee
ms.author: v-dele
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f11b44833ae54c6982cc4df9e2dbd6cb03e7fcd1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54927888"
---
# <a name="nosplash-devenvexe"></a>/NoSplash (devenv.exe)

阻止显示初始屏幕。

## <a name="syntax"></a>语法

```shell
devenv /NoSplash [File1[ FileN]...]
```

## <a name="arguments"></a>自变量

- File1

  可选。 要在现有 Visual Studio 实例中打开的文件。 如果没有 Visual Studio 实例，便会新建包含简化窗口布局的实例，且工具会在新实例中打开 File1。

- FileN

  可选。 要在现有 Visual Studio 实例中打开的一个或多个其他文件。

## <a name="remarks"></a>备注

此开关隐藏初始屏幕。 省略此开关会导致初始屏幕显示。 若要进一步检查初始屏幕（例如，检查 VSPackage 产品图标），请使用 [/Splash](../../extensibility/devenv-command-line-switches-for-vspackage-development.md) 开关。

`/NoSplash` 开关可以与其他开关组合，如 [/Run](run-devenv-exe.md) 或 [/DebugExe](debugexe-devenv-exe.md)。

## <a name="example"></a>示例

所有这三个示例都打开 IDE，而不显示初始屏幕。 第二个示例还编译指定解决方案，并运行已生成的可执行文件。 第三个示例打开指定可执行文件，以供在 IDE 中调试。

```shell
devenv /nosplash

devenv /nosplash /run MySolution.sln

devenv /nosplash /debugexe MySolution.exe
```

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)
- [适用于 VSPackage 开发的 Devenv 命令行开关](../../extensibility/devenv-command-line-switches-for-vspackage-development.md)
