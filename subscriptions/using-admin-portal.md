---
title: 订阅管理门户入门 |Visual Studio Marketplace
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/24/2019
ms.topic: conceptual
description: 了解如何开始在订阅管理门户中管理组织的 Visual Studio 订阅。
ms.openlocfilehash: f3b11a0a0977fff8a6c89f565adffb1cac49e2ad
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605706"
---
# <a name="get-started-with-the-visual-studio-subscriptions-administration-portal"></a>开始使用 Visual Studio 订阅管理门户
使用 Visual Studio 订阅管理门户时，需要记住：
- **Visual Studio 订阅根据用户授权。** 每个订阅者可以根据开发和测试需要在多台计算机上使用软件。
- 为每个订阅者只分配一个订阅级别，分别对应于组织购买的 Visual Studio 订阅。  如果订阅者分配有多个订阅级别，请编辑订阅者的设置，使他们只有一个订阅级别。
- **更新订阅者的订阅级别**，当订阅升级（购买“升级”许可证之后）或续签到更低级别时更新。
- **不要在订阅者之间共享订阅。** 订阅必须分配给指定的个人。  不允许将订阅分配给团队。  必须将订阅分配给任何使用全部或部分订阅权益（开发和测试软件、Microsoft Azure、E-Learning 等）的用户。

## <a name="access-to-the-portal"></a>门户访问权限
如果你是组织协议的主要联系人或通知联系人，则在设置批量许可协议时，你将自动获得门户访问权限。 你将收到系统触发的欢迎电子邮件，它将指示用于登录门户的电子邮件地址。 登录后，你将自动设置为超级管理员，并可以开始管理订阅和其他管理员。 

## <a name="administrator-roles"></a>管理员角色
批量许可客户在新的 Visual Studio 订阅管理门户中存在两种不同的角色。 这些角色就像现在 VLSC 中的“主要联系人或通知联系人”角色和“订阅管理员”角色。

**超级管理员：** 首次设置组织时，“主要联系人或通知联系人”在默认情况下会成为超级管理员。 主要联系人或通知联系人可以选择分配其他超级管理员或管理员。 超级管理员可以添加和删除其他管理员和订阅者。 如果系统中有两个以上的超级管理员，为了安全起见，超级管理员可以删除最后两个以外的所有超级管理员。

**管理员：** 管理员只能由超级管理员设置。管理员可以在超级管理员分配给订阅者的协议中对其进行管理。

## <a name="the-subscribers-page"></a>“订阅者”页
已分配有订阅后，“订阅者”选项卡会提供有关订阅者的详细信息，包括：
- 每个订阅者的名字和姓氏。
- 该用户的电子邮件地址。
- 为其分配的订阅级别。
- 为其分配订阅的日期。
- 订阅的到期日期。
- 可选的文本说明。
- 是否启用或禁用订阅者下载的指示。
- 订阅者所在的国家/地区。
- 订阅者对来自管理门户的分配通信电子邮件的语言首选项。
- 用于通信而不是登录的其他电子邮件地址的可选字段。

在本页左侧，可以看到有关已购买、已分配以及针对每个协议在组织中仍然可用的订阅许可证数量的更多信息。
> [!div class="mx-imgBorder"]
> ![Visual Studio 订阅管理员门户订阅者页](_img/using-admin-portal/subscribers-page.png)

## <a name="the-details-page"></a>“详细信息”页
有关正在查看的协议的更多信息，请选择“详细信息”选项卡。它显示协议状态、购买帐户、组织详细信息、超级管理员和其他相关信息。
> [!div class="mx-imgBorder"]
> ![Visual Studio 订阅管理门户的“详细信息”页](_img/using-admin-portal/details-page.png)

## <a name="next-steps"></a>后续步骤
详细了解管理员的职责：
- [管理员职责概述](admin-responsibilities.md)
- [清点预生产环境](admin-inventory.md)
- [管理大型团队和外部承包商](manage-teams.md)
- [跟踪用户分配和处理订单](assignments-orders.md)
- 使用[最大用量](maximum-usage.md)跟踪购买承诺
