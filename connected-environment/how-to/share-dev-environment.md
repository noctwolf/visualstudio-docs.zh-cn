---
title: 如何共享开发环境 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 3/12/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: 43d23caa039340345372076d02b3c4989cde5b01
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31883158"
---
# <a name="share-a-development-environment"></a>共享开发环境

借助通连环境，你可以与团队中的其他人共享开发环境。 每个开发者都可以在私有空间内工作，无需担心会干扰他人。 此外，在同一环境中协同工作可实现端到端地测试代码，无需创建模拟或模拟依赖项。 请参阅[了解团队开发](../get-started-nodejs-06.md)指南以获取详细信息。

若要为多个开发者建立环境，请执行以下操作：
1. [在 Azure 中创建通连环境](../get-started.md)。 需要拥有对所选 Azure 订阅的“所有者”或“参与者”访问权限。
1. 配置环境的资源组，为每个团队成员[授予参与者访问权限](https://docs.microsoft.com/en-us/azure/active-directory/role-based-access-control-configure)。 可通过运行此命令来检查环境的资源组：`vsce env list`
1. 要求团队成员选择环境以便在其中进行开发。
     * **命令行或 VS Code**：查看你有权访问的现有通连环境：`vsce env list`。 选择环境：`vsce env select`。
     * **Visual Studio IDE**：在 Visual Studio 中打开项目，从“启动设置”下拉列表中选择“适用于 AKS 的通连环境”。 在打开的对话框中，选择现有的开发环境。

![Visual Studio“启动设置”下拉菜单](../images/LaunchSettings.png)