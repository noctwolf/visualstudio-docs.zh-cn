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
ms.openlocfilehash: 91c4da26d202e1a23ff70a7c655f64fd6c05a340
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57875388"
---
# <a name="donotloadprojects-devenvexe"></a>/DoNotLoadProjects (devenv.exe)

打开指定的解决方案，而不加载任何项目。

## <a name="syntax"></a>语法

```shell
devenv /DoNotLoadProjects SolutionName
```

## <a name="arguments"></a>自变量

- *SolutionName*

  必需。 要打开的解决方案的完整路径和名称。

## <a name="example"></a>示例

该示例将打开解决方案 MySln.sln 而不加载任何项目。

```shell
devenv /donotloadprojects MySln.sln

```

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)
