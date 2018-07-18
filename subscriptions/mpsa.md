---
title: Microsoft 产品和服务协议 (MPSA) 中的 Visual Studio 订阅 | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 03/14/2018
ms.topic: Get-Started-Article
description: Microsoft 产品和服务协议 (MPSA) 中的 Visual Studio 订阅
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: a18565a97c0cd85ce42109961592a57c490d92a1
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
ms.locfileid: "30864267"
---
# <a name="visual-studio-subscriptions-in-a-microsoft-products-and-services-agreement-mpsa"></a>Microsoft 产品和服务协议 (MPSA) 中的 Visual Studio 订阅

如果已通过 MPSA 计划购买 Visual Studio 订阅，在成为 Visual Studio 订阅管理员并向用户分配订阅之前，需要注意一些事项。 如果已被设置为管理员，则可以直接转到 Visual Studio 订阅[管理门户](https://manage.visualstudio.com/)。 

如果你是 MPSA 客户，我们将向你介绍一个门户，你可以在此门户中通过 MPSA 管理购买的资产。 这个新门户叫做[业务中心](https://businessaccount.microsoft.com/)，它支持部分相同的功能，还支持一些新的功能，例如批量许可服务中心 (VLSC)。 其中包括查看许可证摘要、订单、下载内容、密钥、用户等。但 MPSA 中 Visual Studio 订阅的行为与云服务非常相似。 业务中心还使用工作帐户（而不是 Microsoft 帐户）登录。 如果组织在使用 Office 365 或 Azure Active Directory 等云服务，且这两项服务中的任意一项或两项使用了你的电子邮件，则该电子邮件已经是工作帐户。 在这种情况下，可以使用组织分配的现有密码注册业务中心。 如果组织未使用云服务，且你的电子邮件不是工作帐户，请不要担心，你仍然可以使用该电子邮件注册业务中心。

此外，成为 Visual Studio 管理员后，应在 Visual Studio 订阅[管理门户](https://manage.visualstudio.com/)中将订阅分配给订阅者。 在 MPSA 中，必须将 Visual Studio 订阅设置为其各自的管理门户，即 Visual Studio 订阅管理门户。 为此，需要将购买帐户关联到租户（即 contoso.onmicrosoft.com）。 

请注意，存在两种类型的租户（托管租户和非托管租户）。 托管租户是指组织已经以管理员的身份对其进行管理的租户。 

非托管租户中没有任何管理员，且不能用于 Office 365 等联机服务。 使用非工作帐户的电子邮件注册业务中心时还会创建非托管租户。 如果注册业务中心时系统要求创建密码，则表明该电子邮件不是工作帐户，而且它创建了一个非托管帐户。

完成租户关联之前，成为 Visual Studio 订阅管理员需满足以下几个要求/执行以下几个步骤。

## <a name="pre-tenant-association-managed-tenant"></a>预租户关联（托管租户）
-   必须是业务中心的已注册用户。
-   必须（至少）是所在租户中的用户管理员或全局管理员。 （如果公司已在使用云服务，这条也同样适用）。 需要具有以上任一角色才能成为 Visual Studio 订阅管理员。
-   必须是所在租户中的全局管理员才能将购买帐户关联到租户。
-   必须是业务中心的帐户管理员或帐户管理者。
-   [Azure](https://portal.azure.com/) 用户配置文件中（或任何其他用户）的“国家或地区”字段需根据所在区域（美国、加拿大等）正确填写。 

> [!NOTE]
> 你中意的 Visual Studio 订阅管理员人选不必是业务中心的用户，他们只需要满足步骤 2 和步骤 5 中的标准即可。

满足上述 5 个步骤中的标准后，可按以下步骤继续将购买帐户关联到租户。
1.  登录[业务中心](https://businessaccount.microsoft.com/)。
2.  单击“帐户”选项卡并选择“关联域”。
3.  选择“购买帐户”（如有多个购买帐户）。
4.  选择“租户”（即 contoso.onmicrosoft.com）。
5.  单击“关联域”。

通常情况下，关联后，系统会在几分钟内将满足所需标准的所有用户都设置为 Visual Studio 订阅管理员。 但是有时可能需要长达 24 小时。 被设置为管理员后就能访问 Visual Studio 订阅管理门户。 如果花费的时间超过 24 小时，请联系 MPSA 支持部门。

> [!NOTE]
> 如果在关联后有新用户满足步骤 2 和步骤 5 中标准，必须联系 MPSA 支持部门。 MPSA 支持部门将帮助你设置新的 Visual Studio 订阅管理员。

## <a name="tenant-association-unmanaged"></a>租户关联（非托管）

如上文第五段中所述，如果用于注册业务中心的电子邮件不是工作帐户（未在 Azure Active Directory“Azure AD”中注册），则帐户关联略有不同。 需执行所谓的“域接管”。 在此过程中，你将成为全局管理员并将租户从非托管变为托管。

有关此过程的更详细说明，请参阅[快速入门指南](https://www.microsoft.com/en-us/Licensing/existing-customer/business-center-training-and-resources.aspx)。 请下载名为“设置和使用联机服务”的指南，该指南将指导你完成域接管。 完成此操作后，购买帐户也会关联到租户。

> [!NOTE]
> 完成域接管过程后，必须遵守“预租户关联（托管）”部分中 5 个步骤的标准。 满足这些标准后，只需联系 MPSA 支持部门设置其他 Visual Studio 订阅管理员即可。

如果需要帮助或有任何问题，可通过电话或电子邮件联系支持部门。

MPSA 支持部门：1-866-200-9611，工作时间：周一至周五，上午 5:30 至下午 5:30（太平洋时间）

电子邮件：ngvlsup@microsoft.com
