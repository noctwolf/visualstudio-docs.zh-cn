---
title: devenv.exe InstallVSTemplates switch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /InstallVSTemplates switch
- /InstallVSTemplates Devenv switch
- InstallVSTemplates switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 529979caa801ace8dd649cf1614f2eeb27ca070b
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2018
---
# <a name="installvstemplates-devenvexe"></a>/InstallVSTemplates (devenv.exe)

/InstallVSTemplates 开关注册位于 \<Visual Studio installation path>\Common7\IDE\ProjectTemplates\ 或 \<Visual Studio installation path>\Common7\IDE\ItemTemplates\ 的项目或项模板，以便能够通过“新建项目”和“添加新项”对话框访问它们。

> [!WARNING]
> 此开关仅支持 Visual Studio 合作伙伴开发。 必须以管理员身份运行 devenv 才能使用 [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) 和 [/InstallVSTemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) 开关。 有关详细信息，请参阅[用户权限](../../ide/user-permissions-and-visual-studio.md)。

## <a name="syntax"></a>语法

```
devenv.exe /InstallVSTemplates
```

## <a name="see-also"></a>请参阅

[Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)