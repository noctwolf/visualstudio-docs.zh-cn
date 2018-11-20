---
title: 实验实例 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- experimental builds
- VSPackages, experimental builds
- VSIP, experimental builds
ms.assetid: ead0df4e-6f88-4b42-9297-581b7902f050
caps.latest.revision: 37
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b529ba3a0ea8b38a27d06e03ce15106cbd7512a5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51787986"
---
# <a name="the-experimental-instance"></a>实验实例
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

为了保证从未经测试的应用程序可能会更改其在 Visual Studio 开发环境，请 VSSDK 提供了可用于试验的实验性空间。 像往常一样，使用 Visual Studio 开发新应用程序，但通过使用此实验实例中运行它们。  
  
 具有一个 VSIX 包每个应用程序将启动在调试模式下的 Visual Studio 实验实例。  
  
 如果你想要启动特定的解决方案之外的 Visual Studio 实验实例，请在命令窗口运行以下命令：  
  
 "*\<Visual studio 安装路径 >* \Common7\IDE\devenv.exe"RootSuffix Exp  
  
> [!NOTE]
>  实验实例写入到注册表`<version number>Exp`和`<version number>Exp_Config`节点。 有关示例的 Visual Studio 2015 的实验性注册表区域是  
>   
>  `HKCU\Software\Microsoft\VisualStudio\14.0Exp` 和 `HKCU\Software\Microsoft\VisualStudio\14.0Exp_Config`  
  
 我们建议在开发时，在实验实例中运行你的扩展。 当您部署该扩展时，它在开发实例中运行。 有关注册应用程序的详细信息，请参阅[注册 Vspackage](../extensibility/internals/registering-vspackages.md)。

