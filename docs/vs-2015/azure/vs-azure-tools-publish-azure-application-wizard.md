---
title: 使用 Visual Studio 发布 Azure 应用程序向导 |Microsoft Docs
description: 了解如何在 Visual Studio 发布 Azure 应用程序向导中配置的各种设置
author: ghogen
manager: douge
assetId: 7d8f1ac9-e439-47e0-a183-0642c4ea1920
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: c9c4104d4d07cab7486038a8787ed0c7759abd60
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001574"
---
# <a name="using-the-visual-studio-publish-azure-application-wizard"></a>使用 Visual Studio 发布 Azure 应用程序向导

开发 Visual Studio 中的 web 应用程序后，你可以使用发布到 Azure 云服务该应用程序**发布 Azure 应用程序**向导。

> [!Note]
> 本文是有关将部署到云服务，而不是网站。 有关部署到网站的信息，请参阅[如何部署 Azure Web Site](https://social.msdn.microsoft.com/Search/windowsazure?query=How%20to%20Deploy%20an%20Azure%20Web%20Site&Refinement=138&ac=4#refinementChanges=117&pageNumber=1&showMore=false)。

## <a name="accessing-the-publish-azure-application-wizard"></a>访问发布 Azure 应用程序向导

您可以访问两种方法，具体取决于你有 Visual Studio 项目类型中的发布 Azure 应用程序向导。

**如果您有一个 Azure 云服务项目：**

1. 创建或在 Visual Studio 中打开 Azure 云服务项目。

1. 在中**解决方案资源管理器**，右键单击项目，并从上下文菜单中，选择**发布**。

**如果未启用适用于 Azure 的 web 应用程序项目：**

1. 创建或在 Visual Studio 中打开 Azure 云服务项目。

1. 在中**解决方案资源管理器**，右键单击项目，并从上下文菜单中，选择**转换** > **转换为 Azure 云服务项目**。 

1. 在中**解决方案资源管理器**，右键单击新创建的 Azure 项目，并从上下文菜单中，选择**发布**。

## <a name="sign-in-page"></a>登录页

![登录页](./media/vs-azure-tools-publish-azure-application-wizard/sign-in.png)

**帐户**-选择一个帐户，或选择**将帐户添加**帐户下拉列表中。

**选择你的订阅**-选择要用于部署的订阅。

## <a name="settings-page---common-settings-tab"></a>设置页-常用设置选项卡

![常用的设置](./media/vs-azure-tools-publish-azure-application-wizard/settings-common-settings.png)

**云服务**-使用下拉列表中，选择现有的云服务，或者选择**&lt;新建 >**，并创建云服务。 数据中心均显示在每个云服务的括号中。 建议的数据中心的云服务的位置是相同的存储帐户 （高级设置） 的数据中心位置。

**环境**-选择**生产**或**过渡**。 如果你想要在测试环境中部署应用程序，请选择过渡环境。 

**生成配置**-选择**调试**或**发行**。

**服务配置**-选择**云**或**本地**。

**为所有角色启用远程桌面**-如果你想要能够远程连接到该服务，请选择此选项。 此选项主要用于故障排除。 有关详细信息，请参阅[使用 Visual Studio 的 Azure 云服务中的角色启用远程桌面连接](/azure/cloud-services/cloud-services-role-enable-remote-desktop-visual-studio)。

**为所有 web 角色启用 Web 部署**-选择此选项可启用 web 部署的服务。 此外必须选择**为所有角色启用远程桌面**选项才能使用此功能。 有关详细信息，请参阅[发布云服务使用 Visual Studio](vs-azure-tools-publishing-a-cloud-service.md)。

## <a name="settings-page---advanced-settings-tab"></a>设置页-高级设置选项卡

![高级设置](./media/vs-azure-tools-publish-azure-application-wizard/settings-advanced-settings.png)

**部署标签**-接受默认名称，或输入所选的名称。 若要将日期追加到部署标签，将复选框处于选中状态。 

**存储帐户**-选择要用于此部署的存储帐户 * *&lt;新建 > 以创建存储帐户。 数据中心均显示在括号内的每个存储帐户。 建议的存储帐户的数据中心位置是与云服务 （常用设置） 的数据中心位置相同。

将应用程序部署的包存储在 Azure 存储帐户。 部署应用程序后，将从存储帐户中删除包。

**失败时删除部署**-选择此选项将使部署删除在发布期间遇到任何错误。 如果想要保留云服务固定的虚拟 IP 地址，则应取消选中。

**部署更新**-如果你想要仅部署更新的组件，请选择此选项。 部署此类型可以比完整部署更快。 如果想要保留云服务固定的虚拟 IP 地址应选中此项。 

**部署更新-设置**-此对话框用于进一步指定要更新的角色的方式。 如果愿意**增量更新**，更新你的应用程序的每个实例，以便应用程序始终可用。 如果愿意**同时更新**，应用程序的所有实例在同一时间进行都更新。 同时更新速度更快，但你的服务可能不可用在更新过程。

![部署设置](./media/vs-azure-tools-publish-azure-application-wizard/deployment-settings.png)

**启用 IntelliTrace** -指定是否想要启用 IntelliTrace。 使用 IntelliTrace，可以在 Azure 中运行时记录的角色实例的大量调试信息。 如果你需要找出问题的原因，可以使用 IntelliTrace 日志来单步执行您的代码从 Visual Studio 好像它在 Azure 中运行。 有关使用 IntelliTrace 的详细信息，请参阅[调试已发布的 Azure 云服务与 Visual Studio 和 IntelliTrace](./vs-azure-tools-intellitrace-debug-published-cloud-services.md)。

**启用分析**-指定是否想要启用性能分析。 Visual Studio 探查器，可以获取你的云服务的运行方式在计算方面的深入分析。 使用 Visual Studio 探查器的详细信息，请参阅[测试 Azure 云服务的性能](./vs-azure-tools-performance-profiling-cloud-services.md)。

**为所有角色启用远程调试器**-指定是否想要启用远程调试。 调试使用 Visual Studio 的云服务的详细信息，请参阅[调试 Azure 云服务或在 Visual Studio 中的虚拟机](./vs-azure-tools-debug-cloud-services-virtual-machines.md)。

## <a name="diagnostics-settings-page"></a>诊断设置页

![诊断设置](./media/vs-azure-tools-publish-azure-application-wizard/diagnostic-settings.png)

诊断，可以进行故障排除的 Azure 云服务 （或 Azure 虚拟机）。 有关诊断的信息，请参阅[针对 Azure 云服务和虚拟机配置诊断](./vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines.md)。 有关 Application Insights 的信息，请参阅[什么是 Application Insights？](/azure/application-insights/app-insights-overview.md)。

## <a name="summary-page"></a>摘要页

![总结](./media/vs-azure-tools-publish-azure-application-wizard/summary.png)

**目标配置文件**-你可以选择从你已选择的设置创建发布配置文件。 例如，可能会创建一个配置文件用于测试环境，另一个用于生产。 若要保存此配置文件，请选择**保存**图标。 该向导创建配置文件，并将其保存在 Visual Studio 项目。 若要修改的配置文件名称，打开**目标配置文件**列表，，然后选择**&lt;管理...&gt;**.

   > [!Note]
   > 发布配置文件出现在解决方案资源管理器在 Visual Studio 中，配置文件设置将写入扩展名为.azurePubxml 的文件。 设置保存为 XML 标记的属性。

## <a name="publishing-your-application"></a>发布你的应用程序

一旦您配置您的项目的部署的所有设置，请选择**发布**在对话框的底部。 你可以监视中的进程状态**输出**Visual Studio 窗口中的。

## <a name="next-steps"></a>后续步骤

- [迁移和发布到 Azure 云服务 Web 应用程序从 Visual Studio](./vs-azure-tools-migrate-publish-web-app-to-cloud-service.md)

- [了解如何使用 Visual Studio 发布 Azure 云服务](./vs-azure-tools-publishing-a-cloud-service.md)

- [调试已发布的 Azure 云服务与 Visual Studio 和 IntelliTrace](./vs-azure-tools-intellitrace-debug-published-cloud-services.md)

- [测试 Azure 云服务的性能](./vs-azure-tools-performance-profiling-cloud-services.md)

- [为 Azure 云服务和虚拟机配置诊断](./vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines.md)。

- [什么是 Application Insights？](/azure/application-insights/app-insights-overview.md)