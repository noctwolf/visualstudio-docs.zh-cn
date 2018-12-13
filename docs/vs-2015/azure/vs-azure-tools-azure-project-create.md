---
title: 使用 Visual Studio 创建 Azure 云服务项目 |Microsoft Docs
description: 了解如何使用 Visual Studio 创建 Azure 云服务项目
author: ghogen
manager: douge
assetId: ec580df7-3dcc-45a9-a1d9-8c110678dfb5
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: 8149f60440becb3c7a8d0dc08b2a1a9c00fb171a
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001586"
---
# <a name="creating-an-azure-cloud-service-project-with-visual-studio"></a>使用 Visual Studio 创建 Azure 云服务项目
Azure Tools for Visual Studio 提供了允许你创建的项目模板[Azure 云服务](/azure/cloud-services/cloud-services-choose-me)，这是一个简单的通用 Azure 服务。 一旦创建项目后，Visual Studio，可配置、 调试和部署到 Azure 云服务。

## <a name="steps-to-create-an-azure-cloud-service-project-in-visual-studio"></a>在 Visual Studio 中创建 Azure 云服务项目的步骤
本节将指导您完成在 Visual Studio 中创建 Azure 云服务项目，具有一个或多个 web 角色。  

1. 以管理员身份启动 Visual Studio。

1. 在主菜单中，选择**文件** > **新建** > **项目**。

1. 选择**云**视觉对象从C#或 Visual Basic 项目模板节点，然后选择**Azure 云服务**从模板列表。

    ![新的 Azure 云服务](./media/vs-azure-tools-azure-project-create/new-project-wizard-for-cloud-service.png)

1. 指定你想要用于开发你的项目的.NET framework 版本。

1. 输入名称和位置为你的项目和解决方案的名称。 

1. 选择“确定”。

1. 在中**新的 Microsoft Azure 云服务**对话框中，选择你想要添加，角色，然后选择右箭头按钮以将其添加到你的解决方案。

    ![选择新的 Azure 云服务角色](./media/vs-azure-tools-azure-project-create/new-cloud-service.png)

1. 若要重命名已添加的角色，请将鼠标悬停在角色上**新的 Microsoft Azure 云服务**对话框中，并从上下文菜单中，选择**重命名**。 也可以在你的解决方案来更改角色 (在**解决方案资源管理器**) 已添加后。

    ![重命名 Azure 云服务角色](./media/vs-azure-tools-azure-project-create/new-cloud-service-rename.png)

Visual Studio Azure 项目解决方案中具有的角色项目关联。 该项目还包括*服务定义文件*并*服务配置文件*:

- **服务定义文件**-定义应用程序，包括所需角色、 终结点和虚拟机大小的运行时设置。 
- **服务配置文件**-配置角色的多少个实例都运行以及为角色定义的设置的值。 

有关这些文件的详细信息，请参阅[使用 Visual Studio 配置 Azure 云服务的角色](vs-azure-tools-configure-roles-for-cloud-service.md)。

## <a name="next-steps"></a>后续步骤
- [在 Azure 云服务项目使用 Visual Studio 中管理角色](./vs-azure-tools-cloud-service-project-managing-roles.md)
