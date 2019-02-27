---
title: 登录 Visual Studio 订阅时遇到的问题 | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 11/07/2018
ms.topic: conceptual
description: 了解登录 Visual Studio 订阅时可能出现的问题
searchscope: VS Subscription
ms.openlocfilehash: 0073ec4193190e56fb5147b5da56898e1a289fd5
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840943"
---
# <a name="issues-signing-in-to-visual-studio-subscriptions"></a>登录 Visual Studio 订阅时遇到的问题
若要使用 Visual Studio 订阅，必须先登录。  根据订阅，你可能已使用 Microsoft 帐户 (MSA) 或 Azure Active Directory (AAD) 标识进行设置。  本文讨论了在登录订阅时可能遇到的一些问题。

## <a name="microsoft-accounts-msa-cannot-be-created-using-workschool-email-addresses"></a>无法使用工作/学校电子邮件地址创建 Microsoft 帐户 (MSA)

在 Azure AD 中配置电子邮件域时，不再允许使用工作/学校电子邮件地址创建新的个人 Microsoft 帐户 (MSA)。 这意味着什么？ 如果你的组织在使用 Microsoft 365 的 Office 365 或其他业务服务时依赖于 Azure AD，且你已向 Azure AD 租户添加了域名，则用户将无法再使用你域中的电子邮件地址创建新的个人 Microsoft 帐户。

### <a name="why-was-this-change-made"></a>为什么要进行此更改？

将工作地址作为用户名的个人 Microsoft 帐户会出现许多最终用户和 IT 部门的问题。 例如:
- 用户可能会认为他们的个人 Microsoft 帐户符合业务要求，并且当他们将业务文档保存到 OneDrive 中时，也是满足符合性的
- 离开组织的用户通常会失去对其工作电子邮件地址的访问权限。 当他们这样做时，如果忘记密码，则可能无法找回他们的个人 Microsoft 帐户。 另一方面，IT 部门可以重置密码并进入前雇员的个人帐户。
- IT 部门对帐户所有权和安全性有一种错觉。 但用户只需将代码往返到工作电子邮件地址一次，则可以在将来随时重命名其帐户。

对于拥有两个具有相同电子邮件地址的帐户（一个 Azure AD 和一个 Microsoft 帐户），情况尤其令人困惑。

### <a name="what-does-this-experience-look-like"></a>这是种什么体验？

如果你尝试使用工作或学校电子邮件地址注册 Microsoft 使用者应用，将看到以下消息。

   > [!div class="mx-imgBorder"]
   > ![无法使用工作电子邮件创建帐户](_img/sign-in-issues/cannot-use-work-email.png)

但是，如果你尝试注册支持个人和工作/学校帐户的 Microsoft 应用，应看到以下消息：

   > [!div class="mx-imgBorder"]
   > ![支持工作或学校帐户](_img/sign-in-issues/existing-account.png)

### <a name="are-existing-accounts-affected"></a>现有帐户是否受影响？
此处描述的注册块仅阻止创建新帐户。 它对已拥有工作/学校电子邮件地址的 Microsoft 帐户的用户没有影响。 如果你已处于这种情况，我们已改进，你可以更轻松地重命名个人 Microsoft 帐户。 这篇[支持文章](http://windows.microsoft.com/en-US/Windows/rename-personal-microsoft-account)提供了简单的逐步指导。 重命名个人 Microsoft 帐户意味着更改用户名，不会影响工作电子邮件或登录到业务服务（如 Office 365）的方式。 它也不会影响个人资料 - 只是改变了登录方式。 你可以使用其他（个人）电子邮件地址，从 Microsoft 获取新的 @outlook.com 电子邮件地址，或将电话号码用作新用户名。

> [!NOTE]
> 如果 IT 部门要求使用工作/学校电子邮件创建个人 Microsoft 帐户，例如访问 Microsoft 业务服务（如顶级支持），请在重命名帐户之前与管理团队联系。

## <a name="deleting-a-sign-in-address-may-prevent-access-to-a-subscription"></a>删除登录地址可能会阻止访问订阅

如果删除与订阅关联的一个或多个标识（MSA 或 AAD），则你的订阅者信息（包括用户名和登录 ID）可能会呈现匿名，从而导致无法访问订阅。

为避免对订阅访问权限产生影响，请使用以下方法之一。
- 部署单一标识管理系统（MSA 或AAD），但不能同时部署这两者。
- 通过租户关联 AAD 和 MSA 标识。


## <a name="next-steps"></a>后续步骤
- 了解如何在 AAD 中[关联 MSA 和 AAD 帐户](/azure/active-directory/b2b/add-users-administrator)。
- 详细了解[授权](anonymization.md)。
