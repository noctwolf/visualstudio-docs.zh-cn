---
title: 修改 Visual Studio
titleSuffix: ''
description: 了解如何逐步修改 Visual Studio。
ms.custom: H1Hack27Feb2017,seodec18
ms.date: 06/12/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- modify Visual Studio
- change visual studio
- changing Visual Studio
- customize Visual Studio
ms.assetid: 3399ea7b-a291-4a9e-80a1-b861a21afa1d
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c11e20343eea33a01c81525855e56078865340e8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53831844"
---
# <a name="modify-visual-studio-2017-by-adding-or-removing-workloads-and-components"></a>通过添加或删除工作负载和组件修改 Visual Studio 2017

我们不但简化了 Visual Studio 的个性化设置，让用户能够轻松匹配所需完成的任务，还简化了 Visual Studio 的自定义操作。 要执行此操作，请启动新的 Visual Studio 安装程序，即可进行所需更改。

操作方法如下。

## <a name="modify-workloads"></a>修改工作负载

 工作负载包含所用编程语言或平台必需的功能。 可以使用工作负载来修改 Visual Studio，以便在需要执行某项操作时为其提供支持。

>[!IMPORTANT]
>若要安装、更新或修改 Visual Studio，必须使用具有管理权限的帐户登录。 有关详细信息，请参阅[用户权限与 Visual Studio](../ide/user-permissions-and-visual-studio.md)。

1. 在计算机上找到 Visual Studio 安装程序。

     例如，在运行 Windows 10 的计算机上，选择“开始”，然后滚动到字母“V”，它作为“Visual Studio 安装程序”在那里列出。

     ![Visual Studio 安装程序](media/vs2017-locate-the-visual-studio-installer.PNG "查找 Microsoft Visual Studio 安装程序")

     >[!NOTE]
     >对于某些计算机，Visual Studio 安装程序可能列在字母 **“M”** 下，即 **Microsoft Visual Studio 安装程序**。<br/><br/> 或者，可以在以下位置找到 Visual Studio 安装程序：`C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

2. 单击或点击以启动安装程序，然后选择“修改”。

     ![启动或修改 Visual Studio](media/modify-visual-studio.png "修改 Visual Studio 2017")

     如果还有更新挂起，则“修改”按钮会出现在其他位置。 这样一来，如果选择执行此操作，可以在不更新的情况下修改 Visual Studio。 单击“更多”，然后选择“修改”。

     ![更新或修改 Visual Studio](media/modify-or-update-visual-studio.png "更新或修改 Visual Studio 2017")

3. 从“工作负载”屏幕中，选择或取消选择要安装或卸载的工作负载。

    ![Visual Studio 2017 设置对话框](media/vs2017-modify-workloads.PNG "选择 Visual Studio 2017 中的工作负载")

4. 再一次选择“修改”。

5. 安装完新的工作负载和组件后，选择“启动”。

## <a name="modify-individual-components"></a>修改各个组件

如果不想使用现成的工作负载功能来自定义 Visual Studio 安装，请从 Visual Studio 安装程序中选择“各个组件”选项，选择所需组件，然后按提示操作。

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>请参阅

* [安装 Visual Studio 2017](install-visual-studio.md)
* [更新 Visual Studio 2017](update-visual-studio.md)
* [卸载 Visual Studio 2017](uninstall-visual-studio.md)
