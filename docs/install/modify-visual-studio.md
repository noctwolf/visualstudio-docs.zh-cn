---
title: 修改 Visual Studio 2017 | Microsoft Docs
description: 了解如何逐步修改 Visual Studio。
ms.custom: H1Hack27Feb2017
ms.date: 11/08/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
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
ms.openlocfilehash: 597da9be2ce4c6d22beaa6fc5fc419ef785ece94
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="modify-visual-studio-2017-by-adding-or-removing-workloads-and-components"></a>通过添加或删除工作负载和组件修改 Visual Studio 2017
我们不但简化了 Visual Studio 的个性化设置，让用户能够轻松匹配所需完成的任务，还简化了 Visual Studio 的自定义操作。 不必再通过控制面板进行修改；而是启动新的 Visual Studio 安装程序，即可进行所需更改。

操作方法如下。  

## <a name="modify-workloads"></a>修改工作负载  
 工作负载包含所用编程语言或平台必需的功能。 可以使用工作负载来修改 Visual Studio，以便在需要执行某项操作时为其提供支持。  

>[!IMPORTANT]
>若要安装、更新或修改 Visual Studio，必须使用具有管理权限的帐户登录。 有关详细信息，请参阅[用户权限与 Visual Studio](../ide/user-permissions-and-visual-studio.md)。

1.  在计算机上找到 Visual Studio 安装程序。  

     例如，在运行 Windows 10 周年更新的计算机上，选择“开始”，然后滚动到字母“V”，其中它作为“Visual Studio 安装程序”列出。  

     ![Visual Studio 安装程序](media/vs2017-locate-the-visual-studio-installer.PNG "查找 Microsoft Visual Studio 安装程序")

     >[!NOTE]
     对于某些计算机，Visual Studio 安装程序可能列在字母**“M”**下，即 **Microsoft Visual Studio 安装程序**。<br/><br/> 或者，可以在以下位置找到 Visual Studio 安装程序：`C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

2.  单击或点击以启动安装程序，然后选择“修改”。  

     ![启动或修改 Visual Studio](media/vs2017-modify.PNG "修改 Visual Studio 2017")  

3.  从“工作负载”屏幕中，选择或取消选择要安装或卸载的工作负载。  

    ![Visual Studio 2017 设置对话框](media/vs2017-modify-workloads.PNG "选择 Visual Studio 2017 中的工作负载")

4. 再次单击或点击“修改”**修改**。  

5. 安装完新的工作负载和组件后，单击“启动”。

## <a name="modify-individual-components"></a>修改各个组件

如果不想使用现成的工作负载功能来自定义 Visual Studio 安装，请从 Visual Studio 安装程序中选择“各个组件”选项，选择所需组件，然后按提示操作。  

## <a name="get-support"></a>获取支持
有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://www.visualstudio.com/vs/support/#talktous)。

下面是另外几个支持选项：
* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题，并在其中提问和找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。  （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅
* [安装 Visual Studio 2017](install-visual-studio.md)
* [更新 Visual Studio 2017](update-visual-studio.md)
* [卸载 Visual Studio 2017](uninstall-visual-studio.md)
