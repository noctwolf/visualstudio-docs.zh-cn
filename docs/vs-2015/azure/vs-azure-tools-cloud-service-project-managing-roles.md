---
title: 在使用 Visual Studio 的 Azure 云服务中管理角色 |Microsoft Docs
description: 了解如何添加和使用 Visual Studio 的 Azure 云服务中删除角色。
author: ghogen
manager: douge
assetId: 5ec9ae2e-8579-4e5d-999e-8ae05b629bd1
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: 35221cbf98f26a71e2b4adf0a7178342616ff7c0
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001558"
---
# <a name="managing-roles-in-azure-cloud-services-with-visual-studio"></a>在使用 Visual Studio 的 Azure 云服务中管理角色
创建 Azure 云服务后，可以向其添加新角色或从中删除现有角色。 此外可以导入现有项目，并将其转换为一个角色。 例如，可以导入 ASP.NET web 应用程序，并将其指定为 web 角色。

## <a name="adding-a-role-to-an-azure-cloud-service"></a>将角色添加到 Azure 云服务
以下步骤将指导你完成将 web 或辅助角色添加到 Visual Studio 中的 Azure 云服务项目。

1. 创建或在 Visual Studio 中打开 Azure 云服务项目。

1. 在中**解决方案资源管理器**，展开项目节点

1. 右键单击**角色**节点以显示上下文菜单。 从上下文菜单中，选择**添加**，然后从当前解决方案中，选择现有 web 角色或辅助角色或创建 web 或辅助角色项目。 此外可以选择适当的项目，如 ASP.NET web 应用程序项目，并将其与角色项目相关联。

    ![将角色添加到 Azure 云服务项目的菜单选项](./media/vs-azure-tools-cloud-service-project-managing-roles/add-role.png)

## <a name="removing-a-role-from-an-azure-cloud-service"></a>从 Azure 云服务删除角色
以下步骤将指导你完成从 Visual Studio 中的 Azure 云服务项目删除 web 或辅助角色。

1. 创建或在 Visual Studio 中打开 Azure 云服务项目。

1. 在中**解决方案资源管理器**，展开项目节点

1. 展开**角色**节点。

1. 右键单击想要删除，并从上下文菜单中，选择的节点**删除**。 

    ![将角色添加到 Azure 云服务的菜单选项](./media/vs-azure-tools-cloud-service-project-managing-roles/remove-role.png)

## <a name="readding-a-role-to-an-azure-cloud-service-project"></a>将角色重新添加到 Azure 云服务项目
如果你从你的云服务项目中删除角色，但后来又决定将角色添加回项目，添加角色声明和基本特性，例如终结点和诊断信息。 没有其他资源或引用添加到`ServiceDefinition.csdef`文件或设置为`ServiceConfiguration.cscfg`文件。 如果你想要添加此类信息，您需要手动将其添加回这些文件。

例如，你可能会删除 web 服务角色和更高版本，您决定将此角色添加回你的解决方案。 如果这样做，就会出错。 若要防止出现此错误，必须添加`<LocalResources>`显示在恢复到下面的 XML 元素`ServiceDefinition.csdef`文件。 使用你添加回项目的 name 属性的一部分的 web 服务角色的名称**<LocalStorage>** 元素。 在此示例中，web 服务角色的名称是**WCFServiceWebRole1**。

    <WebRole name="WCFServiceWebRole1">
        <Sites>
          <Site name="Web">
            <Bindings>
              <Binding name="Endpoint1" endpointName="Endpoint1" />
            </Bindings>
          </Site>
        </Sites>
        <Endpoints>
          <InputEndpoint name="Endpoint1" protocol="http" port="80" />
        </Endpoints>
        <Imports>
          <Import moduleName="Diagnostics" />
        </Imports>
       <LocalResources>
          <LocalStorage name="WCFServiceWebRole1.svclog" sizeInMB="1000" cleanOnRoleRecycle="false" />
       </LocalResources>
    </WebRole>

## <a name="next-steps"></a>后续步骤
- [使用 Visual Studio 配置 Azure 云服务的角色](vs-azure-tools-configure-roles-for-cloud-service.md)
