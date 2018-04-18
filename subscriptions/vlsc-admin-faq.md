---
title: VLSC 管理迁移常见问题解答 | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 03/13/2018
ms.topic: Get-Started-Article
description: 批量许可服务中心管理迁移常见问题解答
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 014564880dcc7587a1f94e3815d6f36edb36cee3
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
# <a name="visual-studio-subscriptions-administration-migration"></a>Visual Studio 订阅管理迁移

在接下来几个月中，Visual Studio 订阅（以前称为 MSDN 订阅）的管理将引来改变。 目前可通过批量许可购买 Visual Studio 订阅，并在批量许可服务中心 (VLSC) 门户中管理该订阅。 我们正在创建新的管理门户，将来在这个新的门户中管理 Visual Studio 订阅。 除 VLSC 提供的现有操作外，在新门户中还可以无限制地批量分配、跟踪和筛选订阅以及利用 Azure Active Directory (Azure AD) 管理访问权限。 新的 Visual Studio 管理门户位于：[https://manage.visualstudio.com](https://manage.visualstudio.com)。 

> [!Note] 
> 此次迁移不会影响 MPSA 客户。 

## <a name="frequently-asked-questions"></a>常见问题

### <a name="why-is-it-changing"></a>为何迁移？
新门户可优化 Visual Studio 订阅管理体验，不论购买方式如何均可创建单一体验来管理 Visual Studio 订阅。 新门户的新平台启用了 Azure AD，为我们的未来做好了准备。 此外，它还更新了用户界面，让界面更易于导航和使用，提高了管理员的工作效率。

### <a name="who-will-be-impacted"></a>谁将受到影响？ 
此次迁移将会影响具有有效批量许可协议和通过批量许可购买 Visual Studio 订阅的所有客户。 

### <a name="when-is-it-changing"></a>何时迁移？
这是一次大规模的迁移，将分阶段完成，直到具有 Visual Studio 订阅的有效批量许可协议的所有客户都迁移到新的管理门户为止。 自 2017 年第一季度开始迁移。 我们会在计划的迁移周之前通知批量许可客户。  

### <a name="does-my-organization-need-to-sign-up-for-azure-active-directory-azure-ad"></a>组织是否需要注册 Azure Active Directory (Azure AD)？
组织无需注册 Azure AD，但你可以随时注册。 如果选择加入到 Azure AD，则通过 Azure AD 免费层即可加入，无需任何费用。 Azure Active Directory 的安全性更高、控制力更强、可靠性更长久，可以用来为组织提供保护。 但如果你尚未做好使用 Azure AD 的准备，则可以继续照旧使用 Microsoft Accounts (MSA)。 

### <a name="how-do-i-know-when-my-organization-will-be-migrated"></a>如何知道组织的迁移时间？
我们会在迁移组织的前一周向主要/通知联系人发送一封电子邮件，邀请他们完成加入过程。 我们也会向订阅管理者发送一封电子邮件，让他们了解我们已联系主要/通知联系人，并详细介绍了帮助确保顺利加入的方法。 了解如何[找到组织的主要/通知联系人](#How-do-I-find-out-who-my-Primary-or-Notices-Contact-is?)。 

### <a name="is-onboarding-different-from-migration"></a>加入与迁移不同吗？
是的。  此过程包括以下两个阶段。 迁移前迁移（或加入）组织可确保管理员的工作不会受到干扰。 组织的信息迁移后，你就能在新门户中管理 Visual Studio 订阅。 如果主要/通知联系人未在迁移之前加入，则在你完成加入过程之前，订阅管理员将被阻止且无法管理订阅。 

### <a name="what-is-the-onboarding-process"></a>什么是加入过程？
主要/通知联系人将收到一封邀请其完成加入过程的电子邮件。 有关该过程的说明，请参阅下文。 
1.  **查找 PCN 并登录：**

    a.  在电子邮件中，向“主要联系人”和“通知联系人”提供了唯一的链接及其公共客户编号 (PCN) 的最后三位数字。* 

    b.  为了获取完整的 PCN，主要联系人需要登录到 VLSC（可在下文中了解如何查找 PCN 的说明）。 

    c.  获得 PCN 后，他们需要选择自己的唯一链接，该链接将提示他们登录。 他们可以使用工作或学校帐户（如果组织在 Azure AD 中）或 Microsoft 帐户 (MSA)（如果组织不在 Azure AD 中）。 

    d.  接下来，系统将提示他们输入 PCN。 

2.  **设置管理员：**

    输入 PCN 后，他们将转到可以添加超级管理员和管理员（以前称为“订阅管理员”）的页面。 在理想情况下，此操作应在组织的迁移日期之前完成，以便订阅管理中断。 

3.  **访问新的订阅管理门户：**组织迁移后，将向超级管理员和管理员发送电子邮件，邀请他们访问新的门户并开始管理订阅。 

> [!NOTE] 
> 如果主要联系人或通知联系人收到多封电子邮件，这意味着他们具有多个 PCN。 他们需要使用每封电子邮件中引用的 PCN 的唯一链接完成该过程。 

### <a name="what-is-the-difference-between-a-super-admin-and-an-administrator"></a>超级管理员和管理员之间有什么区别？
主要/通知联系人首次登录时，系统会将他们自动设置为超级管理员。超级管理员可以通过添加/删除其他超级管理员或管理员来管理管理员对订阅的访问权限，此外还可以管理订阅。 除自己以外，超级管理员还可以选择分配其他超级管理员。

管理员（以前称为“订阅管理员”）只能管理订阅，但无法控制谁有权管理订阅。 

### <a name="how-will-i-as-an-administrator-onboard-to-the-new-portal"></a>我作为管理员应如何加入到新门户？
组织的主要联系人和通知联系人会收到一封的电子邮件，其中只包含一个链接，通过该链接可跳转到能使用工作或学校帐户登录，且由 Azure Active Directory (Azure AD) 或个人 MSA 提供支持的页面。 登录后，他们需要输入组织的公共客户编号 (PCN) 或授权编号来验证协议。 然后系统会将他们设置为可以添加其他管理员（例如你）的超级管理员，以管理 Visual Studio 订阅。 

### <a name="where-do-i-manage-subscriptions-if-my-organization-has-been-onboarded-but-hasnt-been-migrated"></a>如果我的组织已经加入，但尚未迁移，我应该在哪里管理订阅？ 
你可以继续通过 VLSC 管理订阅，直到收到 Visual Studio 订阅的电子邮件，其中说明你的组织已迁移并且可以在新门户中进行管理。 

### <a name="where-can-i-locate-my-organizations-public-customer-number-pcn-or-authorization-number"></a>我可以在哪里找到组织的公共客户编号 (PCN) 或授权编号？
登录到 [VLSC](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 并按以下路径导航：“订阅” > “Visual Studio 订阅”。 PCN 位于“协议/公共客户编号结果”之下。 请参阅这篇[帮助文章](/find-pcn/)，了解查找 PCN 的相关分步指导。 

### <a name="how-do-i-find-out-who-my-primary-or-notices-contact-is"></a>如何找出主要联系人或通知联系人是谁？
登录到 [VLSC](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 并按以下路径导航：“许可证”>“关系汇总”，然后选择“许可 ID”>“联系人”。 请参阅这篇[帮助文章](/find-primary-contact/)，了解查找主要联系人或通知联系人的相关分步指导。 

### <a name="what-if-my-primary-or-notices-contact-is-gone-no-longer-with-the-company-or-not-available-to-complete-onboarding"></a>如果我的主要联系人或通知联系人已离职、不再就职于这家公司或无法完成加入，该怎么办？
你需要[联系支持人员](https://www.visualstudio.com/subscriptions/support/#talktous)并提供在 VLSC 中用于管理订阅的电子邮件。 验证后，支持人员将帮助你执行加入过程。 

### <a name="what-will-happen-with-renewing-customers"></a>续订客户会受到怎样的影响？ 
迁移不会影响续订过程，因此续订客户应继续照常续订其订阅。 

### <a name="should-my-organization-wait-to-set-up-a-new-agreement-in-the-new-system-rather-than-renew-an-existing-agreement"></a>我的组织是否应该等待在新系统中设置新协议，而不能续订现有协议？ 
不是。  迁移不会影响协议的创建或续订。 

### <a name="what-if-my-organizations-agreement-is-in-the-grace-period-during-the-transition-will-they-also-be-migrated"></a>如果迁移期间我组织的协议在宽限期会怎样？ 它们是否也会被迁移？
是，如果协议仍然有效，将迁移组织。 

### <a name="what-if-my-organization-has-over-claimed-in-the-current-system-will-we-still-be-migrated-to-the-new-system"></a>如果我的组织在当前系统中过度索取会怎样？ 是否仍会迁移到新系统？ 
是，你的组织仍然会迁移到新系统。 新系统中将保留过度索取能力（针对允许此操作的协议类型）。 

### <a name="what-if-my-organization-has-more-than-one-subscription-assigned-to-a-single-useremail-address"></a>如果我的组织中有多个订阅分配给了一个用户/电子邮件地址会怎样？
你的组织仍然会迁移。  但你将无法向该用户/电子邮件地址分配任何其他的同级别订阅（即企业版、专业版等）。 迁移后，任何使用相同电子邮件地址的同级别订阅仍然可见，但管理员需更改电子邮件地址，确保其具有唯一性。 新门户中，不能将同级别的多个订阅分配给一个用户/电子邮件地址。

### <a name="where-can-i-find-the-most-up-to-date-information-about-the-migration"></a>在哪里可以找到有关迁移的最新信息？ 
有关此迁移的最新信息，请访问 Visual Studio 订阅管理员[网页](https://aka.ms/vs-admin)。 如需支持，请查看 Visual Studio 订阅[支持页](http://www.visualstudio.com/subscriptions/support/#!collections/962-subscriptions)，其中包含了自助信息和支持人员联系信息。 接下来几个月中，我们将继续在管理员网页上和通过电子邮件提供更新，以帮助轻松完成转换。 

## <a name="resources-and-support-information"></a>资源和支持信息
- [管理员网页](https://www.visualstudio.com/subscriptions-administration/)

- Visual Studio 订阅和管理[支持](https://www.visualstudio.com/subscriptions/support/) 

- [如何查找 PCN](/find-pcn/)

- [如何查找主要联系人或通知联系人](/find-primary-contact/) 

- 加入组织和管理管理员的相关[视频](https://www.youtube.com/watch?v=ZmnywYGSFMg&list=PLReL099Y5nRfDyvvwzNDBaZe7qTxmuM2T&index=1&t=0s) 
