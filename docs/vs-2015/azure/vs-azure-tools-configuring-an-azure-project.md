---
title: 使用 Visual Studio 配置 Azure 云服务项目 |Microsoft Docs
description: 了解如何配置 Azure 云服务项目在 Visual Studio 中，具体取决于你为该项目的要求。
author: ghogen
manager: douge
assetId: 609d6965-05cc-47b1-82dc-c76a92d4f295
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/06/2017
ms.author: ghogen
ms.openlocfilehash: 7417bc117de7dc472f413dd9145944cad2d48bb4
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001571"
---
# <a name="configure-an-azure-cloud-service-project-with-visual-studio"></a>使用 Visual Studio 配置 Azure 云服务项目
你可以配置 Azure 云服务项目，具体取决于你为该项目的要求。 可以设置为以下类别的项目的属性：

- **云服务发布到 Azure** -可以设置属性以确保不会意外删除现有的云服务部署到 Azure。
- **运行或调试本地计算机上的云服务**-可以选择要使用和指示是否要启动 Azure 存储模拟器的服务配置。
- **在创建时验证云服务包**-你可以决定将任意警告视为错误，以便您可以确保云服务包部署未出现任何问题。 

## <a name="steps-to-configure-an-azure-cloud-service-project"></a>若要配置 Azure 云服务项目的步骤
1. 打开或在 Visual Studio 中创建云服务项目

1. 在中**解决方案资源管理器**，右键单击项目，并从上下文菜单中，选择**属性**。
   
1. 在项目的属性页中，选择**开发**选项卡。

    ![项目属性菜单](./media/vs-azure-tools-configuring-an-azure-project/solution-explorer-project-properties-menu.png)

1. 设置**删除现有部署之前进行提示**到**True**。 此设置有助于确保不会意外删除 Azure 中的现有部署

1. 选择所需**服务配置**以指示哪个服务配置你想要在运行或调试本地云服务时使用。 有关如何修改服务配置为角色的详细信息，请参阅[如何使用 Visual Studio 配置 Azure 云服务的角色](./vs-azure-tools-configure-roles-for-cloud-service.md)。

1. 设置**启动 Azure 存储模拟器**到**True**运行或调试本地云服务时启动 Azure 存储仿真程序。

1. 设置**将警告视为错误**到**True**以确保如果包验证错误不能发布。

1. 设置**使用 web 项目端口**到**True**以确保你的 web 角色使用的同一端口每次在 IIS Express 中本地启动。

1. 从 Visual Studio 工具栏中，选择**保存**。

## <a name="next-steps"></a>后续步骤
- [配置 Azure 项目使用多个服务配置](vs-azure-tools-multiple-services-project-configurations.md)

