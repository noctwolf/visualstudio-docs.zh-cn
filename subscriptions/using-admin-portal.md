---
title: 使用管理员门户 | Visual Studio Marketplace
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: Get-Started-Article
description: 了解如何使用管理员门户管理组织的 Visual Studio 订阅。
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 956670d624a5c36547a23a06773e7ee254acd7f4
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2018
ms.locfileid: "39380813"
---
#  <a name="using-the-visual-studio-subscriptions-administrator-portal"></a>使用 Visual Studio 订阅管理员门户

使用 Visual Studio 订阅管理门户时，需要记住：
 
- **Visual Studio 订阅根据用户授权。** 每个订阅者可以根据开发和测试需要在多台计算机上使用软件。 
- 为每个订阅者只分配一个订阅级别，分别对应于组织购买的 Visual Studio 订阅。 如果订阅者分配有多个订阅级别，请编辑订阅者的设置，使他们只有一个订阅级别。 
- **更新订阅者的订阅级别**，当订阅升级（购买“升级”许可证之后）或续签到更低级别时更新。 
- **不要在订阅者之间共享订阅。** 必须将订阅分配给任何使用全部或部分订阅权益（开发和测试软件、Microsoft Azure、E-Learning 等）的用户。 

## <a name="administrator-roles"></a>管理员角色

批量许可客户在新的 Visual Studio 订阅管理门户中存在两种不同的角色。 这些角色就像现在 VLSC 中的“主要联系人或通知联系人”角色和“订阅管理员”角色。 

**超级管理员：** 首次设置组织时，“主要联系人或通知联系人”在默认情况下为超级管理员。 主要联系人或通知联系人可以选择分配其他超级管理员或管理员。 超级管理员可以添加和删除其他管理员和订阅者。 如果系统中有两个以上的超级管理员，为了安全起见，超级管理员可以删除最后两个以外的所有超级管理员。 

**管理员：** 管理员只能由超级管理员设置。管理员可以在超级管理员分配给订阅者的协议中对其进行管理。 

## <a name="getting-started"></a>入门

为了使用管理员门户管理组织的订阅，必须首先将组织加入到门户。  完成加入后，你需要熟悉“订阅者”和“详细信息”页面，因为在这些页面可以找到执行订阅管理任务所需的工具和信息。  

### <a name="onboarding"></a>加入

当你的组织已准备好要加入到 Visual Studio 订阅管理门户时，将向主要联系人和通知联系人发送电子邮件，邀请他们完成加入过程。 下面的详细信息是加入到新门户需要进行的步骤。 如果想要演练该过程，请查看此[管理员加入视频](https://channel9.msdn.com/Series/Visual-Studio-Subscriptions-Administration/Onboarding-your-organization-to-the-new-Visual-Studio-Subscription-Administration-Portal-and-setting)或此[支持文章] (https://support.microsoft.com/help/4013931/visual-studio-subscriptions-administrator-migration-process "Visual Studio 订阅：管理员迁移的过程")。   
1.  **查找 PCN 并登录：**
    - 在电子邮件中，向“主要联系人”和“通知联系人”提供了唯一的链接及其公共客户编号 (PCN) 的最后三位数字。 * 
    - 若要获取完整的 PCN，主要联系人需要登录到 VLSC（可在此处找到如何查找 PCN 的说明）。 
    - 获得 PCN 后，他们需要选择自己的唯一链接，该链接将提示他们登录。 他们可以使用工作或学校帐户（如果组织在 AAD 中）或 Microsoft 帐户 (MSA)（如果组织不在 AAD 中）。 
    - 接下来，他们需要输入 PCN。 
2.  **设置管理员。** 输入 PCN 后，他们将在新系统中注册为超级管理员，并且可以添加其他超级管理员和管理员（以前称为“订阅管理员”）。 为避免丢失访问权限，应在组织迁移日期之前完成此操作。 
3.  **访问新的订阅管理门户。**  组织迁移后，将向新添加的超级管理员和管理员发送电子邮件，邀请他们访问新的门户并开始管理订阅。  

> [!NOTE]
> 如果主要联系人或通知联系人收到多封电子邮件，这意味着他们具有多个 PCN。 他们需要使用每封电子邮件中引用的 PCN 的唯一链接完成该过程。*

如果需要添加到新的 Visual Studio 订阅管理门户中，并且不确定谁是主要联系人或通知联系人，那么可以在登录 [VLSC](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 后查找这些信息。 查看[查找你的主要联系人](find-primary-contact.md)主题，了解在 VLSC 中查找主要/通知联系人的步骤。
如果已设置为管理员，则可以直接转到 [Visual Studio 订阅管理门户](https://manage.visualstudio.com)。

### <a name="understanding-the-subscribers-page"></a>了解“订阅者”页
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
    ![Visual Studio 订阅管理员门户订阅者页](_img/using-admin-portal/subscribers-page.png)

### <a name="understanding-the-details-page"></a>了解“详细信息”页
有关正在查看的协议的更多信息，请选择“详细信息”选项卡。该选项卡显示协议状态、购买帐户、组织详细信息、主要联系人 (VLSC)、超级管理员（如果可用）和其他相关信息。
    ![Visual Studio 订阅管理门户的“详细信息”页](_img/using-admin-portal/details-page.png)

