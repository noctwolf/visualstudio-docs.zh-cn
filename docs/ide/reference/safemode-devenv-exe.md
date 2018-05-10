---
title: -SafeMode (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2c678d7304c879cf42c24de9d83704971043676
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
在安全模式下启动 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]，仅加载默认环境和服务。

## <a name="syntax"></a>语法

```cmd
devenv /SafeMode
```

## <a name="remarks"></a>备注
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 启动时，此开关可阻止所有第三方 VSPackages 加载，以此确保执行稳定。

## <a name="description"></a>描述
 以下示例在安全模式下启动 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。

## <a name="code"></a>代码

```cmd
Devenv.exe /SafeMode
```

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)