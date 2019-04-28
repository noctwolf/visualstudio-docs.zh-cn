---
title: -DoNotLoadProjects (devenv.exe)
ms.date: 03/11/2019
ms.topic: reference
helpviewer_keywords:
- Devenv, /DoNotLoadProjects switch
- /DoNotLoadProjects Devenv switch
- DoNotLoadProjects Devenv switch
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de757e7022339b11f6d7c04ea7315abf685da24c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63428047"
---
# <a name="donotloadprojects-devenvexe"></a>/DoNotLoadProjects (devenv.exe)

打开指定的解决方案，而不加载任何项目。 有关详细信息，请参阅 [Visual Studio 中筛选的解决方案](../filtered-solutions.md)。

## <a name="syntax"></a>语法

```shell
devenv /DoNotLoadProjects SolutionName
```

## <a name="arguments"></a>自变量

*SolutionName*

必需。 要打开的解决方案的完整路径和名称。

## <a name="example"></a>示例

该示例将打开解决方案 MySln.sln 而不加载任何项目。

```shell
devenv /donotloadprojects MySln.sln
```

## <a name="see-also"></a>请参阅

- [Visual Studio 中筛选的解决方案](../filtered-solutions.md)
- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)
