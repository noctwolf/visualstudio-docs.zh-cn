---
title: 在 Visual Studio for Mac 中设置多个启动项目
description: 本文介绍如何设置多个要在运行或调试时启动的项目。
author: sayedihashimi
ms.author: sayedha
ms.date: 02/21/2019
ms.topic: conceptual
ms.prod: visual-studio-mac
ms.assetid: fd354fff-ce6b-4505-a815-84a2311e39ba
ms.openlocfilehash: 65b44dddfdadcb7ef38332fa35443dbaeededb5d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152910"
---
# <a name="how-to-set-multiple-startup-projects"></a>如何：设置多个启动项目

通过 Visual Studio for Mac 可指定在调试或运行解决方案时启动多个项目。

## <a name="to-set-multiple-startup-projects"></a>设置多个启动项目

1.  在“Solution Pad”中，选择解决方案（最高层节点）。

2. 选择解决方案节点的上下文（右键单击）菜单，然后选择“设置启动项目...”。

   ![设置启动项目上下文菜单](media/startup-proj-ctx-menu.png)

3. “创建解决方案运行配置”对话框随即显示。 此对话框中，将为解决方案创建新的命名解决方案运行配置。 可以根据喜好命名，默认名称为 `Multiple Projects`。

   ![“创建解决方案运行配置”对话框](media/create-sln-run-config.png)

4. 单击“创建运行配置”。 “解决方案选项”对话框将与所选的新解决方案运行配置一起打开。

   ![“解决方案选项”对话框](media/sln-options-run-config-multi-projects.png)

5. 选择从 Visual Studio for Mac 调试或运行应用程序时要启动的项目。

   ![带有已配置的运行配置的解决方案选项对话框](media/sln-options-run-config-multi-projects-configured.png)

6. 单击 **“确定”**。 将关闭该对话框，并且新的解决方案运行配置将设置为可用的运行配置。

   ![配置为在调试或运行时启动多个项目的解决方案](media/startup-project-configured.png)两个项目都配置为启动，因为它们在 Solution Pad 中都以粗体显示。 在工具栏中，将新的运行配置配置为当前的解决方案运行配置。

## <a name="next-steps"></a>后续步骤

- [在 Visual Studio for Mac 中编译和生成](compiling-and-building.md)
- [了解生成配置](configurations.md)