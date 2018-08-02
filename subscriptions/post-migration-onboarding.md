---
title: 迁移组织后载入到 Visual Studio 订阅管理门户
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 07/12/2018
Ms.topic: Get-Started-Article
Description: Learn how to successfully onboard your organization for Visual Studio subscriptions after migrating to the administration portal.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: c6f0f3de58f2f9f7d532a7b1b84520644fbdb1c7
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "39234756"
---
# <a name="onboarding-to-the-visual-studio-subscriptions-administration-portal-after-your-organization-was-migrated"></a>迁移组织后载入到 Visual Studio 订阅管理门户 

如果在批量许可服务中心 (VLSC) 中管理 Visual Studio 订阅，并且最近访问过该站点以管理订阅，你会注意到 VLSC 中不再提供订阅管理。 管理订阅的过程如下所示：

![VLSC 订阅](_img/post-migration-onboarding/vlsc-subscriptions.png)

到达订阅页面后，你可能会单击下面的链接。 

![关系摘要链接](_img/post-migration-onboarding/relationship-summary-link.png)

此链接以前会将你转到可以管理订阅的页面。   但是，现在通过称为“Visual Studio 订阅管理门户”的新门户管理订阅。  主要联系人或通知联系人需要针对贵组织的批量许可协议采取几个步骤。 如果主要联系人或通知联系人未完成此过程或不再可用，则可能会出现一些情况。 以下内容将指导你完成访问管理订阅的要采取的步骤。 

你可能会遇到以下几种情况之一：
1.  [主要联系人未完成载入流程](#Onboarding-not-completed-by-Primary-Contact)<sup>1</sup> 
2.  [主要联系人已完成载入，但未将你添加为管理员。你的凭据已在 VLSC 中列出。](#Primary-Contact-did-not-provide-you-administrator-access) 
3.  [主要联系人已完成载入，但未将你添加为管理员且你的凭据未在 VLSC 中列出](#Your-credentials-were-not-listed-in-VLSC-prior-to-migration)  

<sup>1</sup> 如果你是主要联系人或通知联系人，并且未完成载入流程，则需要按照第一种情况中的步骤设置组织。 

以下是针对每种情况你预期可以看到的屏幕示例以及可以采取的步骤。 

## <a name="onboarding-not-completed-by-primary-contact"></a>主要联系人未完成载入

如果主要联系人未完成载入体验，你预期可以看到下面的屏幕。 如果你有权访问[批量许可服务中心 (VLSC)](https://www.microsoft.com/Licensing/servicecenter/default.aspx)，则能够完成此流程并获得访问权限以管理订阅。 你将需要组织的[公共客户编号 (PCN)](find-pcn.md)，这可在 VLSC 中找到。 

如果主要联系人未完成载入流程，则只需在字段中输入 [PCN](find-pcn.md) 并选择“发送邀请”。 

![发送邀请电子邮件](_img/post-migration-onboarding/send-invitation.png)

单击该按钮发送邀请后，你将收到一封电子邮件，其中含有完成载入流程的唯一链接。 你需要单击该电子邮件中的链接，使用你的电子邮件地址登录，然后再次输入 PCN。 通过电子邮件中的唯一链接，可以访问 Visual Studio 订阅管理门户。 然后，你将能够访问和管理订阅。 

![电子邮件成功](_img/post-migration-onboarding/email-success.png)


## <a name="primary-contact-did-not-provide-you-administrator-access"></a>主要联系人未提供给你管理员访问权限

如果你的主要联系人已完成载入流程并且你的凭据以前已在 VLSC 中，但主要联系人未提供给你访问权限，则在登录 [Visual Studio 订阅管理门户](https://manage.visualstudio.com/)时，你将看到以下通知。  若要成为管理员，你需要联系屏幕上列出的你所在组织的超级管理员之一。

![管理员列表](_img/post-migration-onboarding/admin-list.png)

## <a name="your-credentials-were-not-listed-in-vlsc-prior-to-migration"></a>迁移前你的凭据未在 VLSC 中列出

如果你的主要联系人已完成载入，但未将你添加为用户并且你的凭据以前未在 VLSC 中列出，则在尝试访问 [Visual Studio 订阅管理门户](https://manage.visualstudio.com/)时，你将看到以下通知。 你将需要联系你的[主要联系人](find-primary-contact.md)才能访问该门户。 

![找不到你](_img/post-migration-onboarding/cant-find-you.png)