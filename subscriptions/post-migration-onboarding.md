---
title: 迁移后载入到 Visual Studio 订阅管理门户
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 07/12/2018
ms.topic: conceptual
description: 了解如何在迁移到管理门户后为 Visual Studio 订阅成功载入组织。
searchscope: VS Subscription
ms.openlocfilehash: 1862361ec6ce38acc3376d972c29d56c5aa7bd51
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56842151"
---
# <a name="onboard-to-the-visual-studio-subscriptions-administration-portal-after-your-organization-is-migrated"></a>迁移组织后载入到 Visual Studio 订阅管理门户

如果你将 Visual Studio 订阅托管在 Microsoft 批量许可服务中心 (VLSC) 内，并且最近访问过此网站以管理订阅，你会发现无法再在 VLSC 中管理订阅。 管理订阅的过程如下所示：
> [!div class="mx-imgBorder"]
> ![突出显示“订阅”选项卡的 Microsoft VLSC 屏幕截图](_img/post-migration-onboarding/vlsc-subscriptions.png)

但是，现在通过称为“Visual Studio 订阅管理门户”的新门户管理订阅。 此流程通常是由组织的批量许可协议的主要联系人或通知联系人完成。 如果仍无法管理，请参阅下面的信息，以获取订阅管理权限。

可能会遇到以下几种情况之一：

1. [主要联系人未完成加入流程。](#Onboarding-not-completed-by-Primary-Contact)<sup>1</sup>
2. [主要联系人已完成加入流程，但未将你添加为管理员。你的凭据已在 VLSC 中列出。](#Primary-Contact-did-not-provide-you-administrator-access)
3. [主要联系人已完成加入流程，但未将你添加为管理员。你的凭据未在 VLSC 中列出。](#Your-credentials-were-not-listed-in-VLSC-prior-to-migration)

<sup>1</sup>如果你是主要联系人或通知联系人，但并未完成加入流程，必须按照第一种情况中的步骤操作来设置组织。

以下各部分详细介绍了上述每种情况。

## <a name="onboarding-not-completed-by-primary-contact"></a>主要联系人未完成加入流程

如果主要联系人未完成加入体验，你会看到下面的屏幕。 如果有权访问[批量许可服务中心 (VLSC)](https://www.microsoft.com/Licensing/servicecenter/default.aspx)，便能完成此流程并获取订阅管理权限。 需要用到组织的[公共客户编号 (PCN)](find-pcn.md)（位于 VLSC 中）。

在“PCN”字段中输入 [PCN](find-pcn.md)，再选择“发送邀请电子邮件”。
> [!div class="mx-imgBorder"]
> ![Visual Studio 订阅管理门户屏幕截图](_img/post-migration-onboarding/send-invitation.png)

此时，你会收到一封电子邮件，其中包含用于完成加入流程的唯一链接。 单击电子邮件中的链接，使用电子邮件地址进行登录，再重新输入 PCN。 通过电子邮件中的唯一链接，可以访问 Visual Studio 订阅管理门户。 然后，你便能访问并管理订阅了。
> [!div class="mx-imgBorder"]
> ![“成功”通知的屏幕截图](_img/post-migration-onboarding/email-success.png)

## <a name="primary-contact-did-not-provide-you-administrator-access"></a>主要联系人未向你授予管理员访问权限

如果主要联系人完成了加入流程，且你的凭据之前位于 VLSC 中，但主要联系人未向你授予访问权限，你会看到以下通知。 请联系通知中列出的一位组织超级管理员，以成为管理员。
> [!div class="mx-imgBorder"]
> ![显示超级管理员列表的 Visual Studio 订阅管理门户屏幕截图](_img/post-migration-onboarding/admin-list.png)

## <a name="your-credentials-were-not-listed-in-vlsc-prior-to-migration"></a>迁移前你的凭据未在 VLSC 中列出

如果主要联系人已完成加入流程，但未将你添加为用户且你的凭据之前未在 VLSC 中列出，你会看到以下通知。 请联系[主要联系人](find-primary-contact.md)，以获取对门户的访问权限。
> [!div class="mx-imgBorder"]
> ![显示“找不到你”通知的 Visual Studio 订阅管理门户屏幕截图](_img/post-migration-onboarding/cant-find-you.png)