---
title: 显示在 VLSC 中的个人电子邮件
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/23/2018
ms.topic: Get-Started-Article
description: Visual Studio 订阅 – 为什么我会在我的订阅者中看到 Hotmail 或 Gmail 地址？
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: cfe035d82976e3df683f4e3a35bd9d7f3c8cf9e2
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
# <a name="visual-studio-subscriptions--why-am-i-seeing-hotmail-or-gmail-addresses-for-my-subscribers"></a>Visual Studio 订阅 – 为什么我会在我的订阅者中看到 Hotmail 或 Gmail 地址？ 

随着公司从批量许可服务中心 (VLSC) 迁移到新的 Visual Studio [订阅管理门户](https://manage.visualstudio.com)，管理员可能会很惊奇地发现某些订阅者的“登录电子邮件地址”显示 Hotmail、Gmail 或 Yahoo 之类的第三方电子邮件地址。

## <a name="cause"></a>原因

由于登录进程与旧版 msDN 订阅者体验相关联，因此会出现这种情况。 用户在没有修改的情况下从 VLSC 迁移到了新门户。 有些管理员可能没有意识到，用户一直在使用个人帐户来访问他们的订阅权益。 在 Visual Studio 订阅者迁移之前（已于 2016 年完成迁移），要成功使用 Visual Studio 订阅需执行以下两个操作：
1. 管理员通过订阅者的工作或学校电子邮件地址，将订阅“分配”给每个订阅者。
2. 订阅者“激活”订阅。

在订阅者激活期间：需要登录 Microsoft 帐户 (msA)。 如果订阅者未尝试使其工作或学校帐户（例如John@contoso.com）成为 MSA，他们可以创建一个新的 MSA，或利用现有 MSA。 这将导致他们的“登录电子邮件地址”不同于其“分配到的电子邮件地址”。

> [!NOTE] 
> [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) 上的新订阅者体验支持工作/学校和 Microsoft 帐户 (msA) 标识类型。

最后，因为管理员迁移从 VLSC 获取有关订阅者“登录电子邮件地址”的数据，用来填充新的订阅者管理体验，最近迁移的管理员可能会看到之前被忽视的个人帐户，因为 UI 发生了变化，使得该信息更为显眼。

## <a name="solution"></a>解决方案

若要解决此问题，你将需要编辑订阅者信息以更新其登录电子邮件地址。  可逐个编辑订阅者，或以批量方式进行编辑。 有关完整信息，请访问[编辑订阅](/visualstudio/subscriptions/edit-license)。  

一旦更新订阅者电子邮件地址，你需要通知他们其登录信息已更改。  