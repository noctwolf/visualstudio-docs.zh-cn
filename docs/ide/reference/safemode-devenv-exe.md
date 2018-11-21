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
ms.openlocfilehash: 6df78ec4be1fc94951634b84a98e80dc1403a41b
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948733"
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