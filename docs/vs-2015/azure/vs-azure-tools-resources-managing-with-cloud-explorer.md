---
title: 使用云资源管理器管理 Azure 资源 |Microsoft Docs
description: 了解如何使用云资源管理器来浏览和管理 Visual Studio 中的 Azure 资源。
author: ghogen
manager: douge
assetId: 6347dc53-f497-49d5-b29b-e8b9f0e939d7
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/25/2017
ms.author: ghogen
ms.openlocfilehash: a5b75aa5e1310e02befe162199472eef987d7cd9
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001272"
---
# <a name="manage-the-resources-associated-with-your-azure-accounts-in-visual-studio-cloud-explorer"></a>在 Visual Studio Cloud Explorer 中管理与你的 Azure 帐户关联的资源

云资源管理器，可查看你的 Azure 资源和资源组、 检查其属性，以及执行重要的开发人员诊断操作从 Visual Studio 中。 

像[Azure 门户](http://go.microsoft.com/fwlink/p/?LinkID=525040)，云资源管理器基于 Azure 资源管理器堆栈。 因此，云资源管理器可以识别 Azure 资源组等资源和逻辑应用和 API 应用等 Azure 服务并支持[基于角色的访问控制](/azure/role-based-access-control/role-assignments-portal.md)(RBAC)。 

## <a name="prerequisites"></a>系统必备

* 使用 visual Studio 2015 [Microsoft Azure SDK for.NET 2.9](https://www.microsoft.com/en-us/download/details.aspx?id=51657)。
* Microsoft Azure 帐户-如果还没有帐户，则可以[注册免费试用版](http://go.microsoft.com/fwlink/?LinkId=623901)或[激活 Visual Studio 订户权益](http://go.microsoft.com/fwlink/?LinkId=623901)。

> [!NOTE]
> 若要查看云资源管理器中，选择**视图** > **云资源管理器**菜单栏上。

## <a name="add-an-azure-account-to-cloud-explorer"></a>添加 Azure 帐户添加到云资源管理器

若要查看与 Azure 帐户关联的资源，必须先将帐户添加到云资源管理器。 

1. 在中**云资源管理器**，选择**Azure 帐户设置**。

   ![云资源管理器 Azure 帐户设置图标](./media/vs-azure-tools-resources-managing-with-cloud-explorer/azure-account-settings.png)

1. 选择**管理帐户**。 

   ![云资源管理器中添加帐户链接](./media/vs-azure-tools-resources-managing-with-cloud-explorer/manage-accounts-link.png)

1. 你想要浏览其的资源登录到 Azure 帐户。 

1. 登录到 Azure 帐户，将显示与该帐户关联的订阅。 选中你想要浏览并选择的帐户订阅的复选框**应用**。 

   ![云资源管理器： 选择要显示的 Azure 订阅](./media/vs-azure-tools-resources-managing-with-cloud-explorer/select-subscriptions.png)

1. 选择后你想要浏览其资源的订阅，这些订阅和资源显示在云资源管理器。

   ![Cloud Explorer 资源列表 Azure 帐户](./media/vs-azure-tools-resources-managing-with-cloud-explorer/resources-listed.png)

## <a name="remove-an-azure-account-from-cloud-explorer"></a>从 Cloud Explorer 删除 Azure 帐户 

1. 在中**云资源管理器**，选择**帐户管理**。

   ![云资源管理器 Azure 帐户设置图标](./media/vs-azure-tools-resources-managing-with-cloud-explorer/azure-account-settings.png)

1. 你想要删除的帐户，旁边选择**管理帐户**。

   ![云资源管理器 Azure 帐户设置图标](./media/vs-azure-tools-resources-managing-with-cloud-explorer/remove-account.png)

1. 选择**删除**若要删除的帐户。

    ![云资源管理器管理帐户对话框中](./media/vs-azure-tools-resources-managing-with-cloud-explorer/accountmanage.PNG)

## <a name="view-resource-types-or-resource-groups"></a>查看资源类型或资源组

若要查看 Azure 资源，可以选择任一**资源类型**或**资源组**视图。

1. 在中**云资源管理器**，选择资源视图下拉列表。

   ![云资源管理器下拉列表选择所需的资源视图](./media/vs-azure-tools-resources-managing-with-cloud-explorer/resources-view-dropdown.png)

1. 从上下文菜单中，选择所需的视图： 

   * **资源类型**视图-上使用的常用视图[Azure 门户](http://go.microsoft.com/fwlink/p/?LinkID=525040)，显示 Azure 资源按类型，例如 web 应用、 存储帐户和虚拟机。 
   * **资源组**视图-Azure 资源分类与它们关联的 Azure 资源组。 资源组是一个 Azure 资源，通常由特定应用程序的捆绑包。 若要了解有关 Azure 资源组的详细信息，请参阅[Azure 资源管理器概述](/azure/azure-resource-manager/resource-group-overview)。

   下图显示了两个资源视图的比较：

   ![云资源管理器资源视图比较](./media/vs-azure-tools-resources-managing-with-cloud-explorer/resource-views-comparison.png)

## <a name="view-and-navigate-resources-in-cloud-explorer"></a>查看和导航资源在云资源管理器

若要导航到 Azure 资源和云资源管理器中查看其信息，展开项的类型或关联的资源组，然后选择相应资源。 当选择资源时，信息会显示在两个选项卡-**操作**并**属性**-在云资源管理器的底部。

* **操作**选项卡-列出了可以针对所选的资源来在云资源管理器中执行的操作。 此外可以通过右键单击要查看其上下文菜单的资源查看这些选项。

* **属性**选项卡-显示资源，例如其类型、 区域设置和资源组，它与之关联的属性。

下图显示您所见的每个选项卡为应用服务的示例的比较：

  ![云资源管理器的屏幕截图](./media/vs-azure-tools-resources-managing-with-cloud-explorer/actions-and-properties.png)

每个资源具有 action**在门户中打开**。 云资源管理器时选择此操作，显示在所选的资源[Azure 门户](http://go.microsoft.com/fwlink/p/?LinkID=525040)。 **在门户中打开**功能适用于导航到深度嵌套的资源。

其他操作和属性值也可能显示基于 Azure 资源。 例如，web 应用和逻辑应用还执行相应的操作**在浏览器中打开**并**将调试器附加**除了**在门户中打开**。 选择存储帐户 blob、 队列或表时，将显示操作以打开编辑器。 Azure 应用具有**URL**并**状态**属性，而存储资源具有键和连接字符串属性。

## <a name="find-resources-in-cloud-explorer"></a>在云资源管理器中查找资源

若要在 Azure 帐户订阅中查找具有特定名称的资源，请输入中的名称**搜索**框在云资源管理器。

  ![在云资源管理器中查找资源](./media/vs-azure-tools-resources-managing-with-cloud-explorer/search-for-resources.png)

输入中的字符**搜索**框中，只有符合这些字符的资源才会显示在资源树中。
