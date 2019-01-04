---
title: 实验实例 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- experimental builds
- VSPackages, experimental builds
- VSIP, experimental builds
ms.assetid: ead0df4e-6f88-4b42-9297-581b7902f050
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cacee26fb84774eb7f1043d940419561bc55ec36
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53917366"
---
# <a name="the-experimental-instance"></a>实验实例
为了保证从未经测试的应用程序可能会更改其在 Visual Studio 开发环境，请 VSSDK 提供了可用于试验的实验性空间。 像往常一样，使用 Visual Studio 开发新应用程序，但通过使用此实验实例中运行它们。  
  
 具有一个 VSIX 包每个应用程序将启动在调试模式下的 Visual Studio 实验实例。  
  
 如果你想要启动特定的解决方案之外的 Visual Studio 实验实例，请在命令窗口运行以下命令：  
  
 "*\<Visual studio 安装路径 >* \Common7\IDE\devenv.exe"RootSuffix Exp  
  
> [!NOTE]
>  实验实例写入到注册表`<version number>Exp`和`<version number>Exp_Config`节点。 有关示例的 Visual Studio 2015 的实验性注册表区域是  
>   
>  `HKCU\Software\Microsoft\VisualStudio\14.0Exp` 和 `HKCU\Software\Microsoft\VisualStudio\14.0Exp_Config`  
  
 我们建议在开发时，在实验实例中运行你的扩展。 当您部署该扩展时，它在开发实例中运行。 有关注册应用程序的详细信息，请参阅[注册 Vspackage](../extensibility/internals/registering-vspackages.md)。