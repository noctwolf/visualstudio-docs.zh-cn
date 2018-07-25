---
title: Visual Studio 订阅者标识
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 04/10/2018
ms.topic: conceptual
description: 如何向 Visual Studio 订阅添加备用标识以用于 VSTS 和 Azure
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: vs subscription
ms.openlocfilehash: 70d11f83584d776fef9dae7e771bcdeb40a3c477
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326301"
---
# <a name="identities-for-visual-studio-subscribers"></a>Visual Studio 订阅者标识

激活 Visual Studio 订阅时，我们会将用户激活期间使用的标识（或登录名）与 Visual Studio 订阅关联起来。 这样，就可以在 [Visual Studio 订阅者门户](https://my.visualstudio.com?wt.mc_id=o~msft~docs)、Visual Studio Team Services (VSTS) 和 Azure 中识别出该用户。

在 VSTS 中，我们会在用户每次登录时检查其 Visual Studio 订阅状态，并在其所属的每个帐户中自动授予相应功能。
因为这些功能包含在订阅者权益中，所以在使用链接到 Visual Studio 订阅的身份时，可以将用户添加为任何 VSTS 帐户中的成员。

在 Azure 中，用户激活其[每月 Azure 额度](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/)（一项订阅者权益）时，我们会检查其 Visual Studio 订阅状态。

在 [Visual Studio 订阅者门户](https://my.visualstudio.com?wt.mc_id=o~msft~docs)中，除激活过程中使用的标识外，还可添加“备用标识”。 现在，如果使用 Microsoft 帐户激活订阅，则可添加备用标识。 通过这种方式，用户还可添加工作或学校帐户（登录 Visual Studio、Office 365 或公司/学校网络时使用的帐户），从而允许用户使用个人帐户和工作或学校帐户访问 VSTS。

## <a name="add-an-alternate-account-to-your-visual-studio-subscription"></a>向 Visual Studio 订阅添加备用帐户

在 Visual Studio 订阅中添加备用帐户后，可访问订阅权益，如 Visual Studio Team Services (VSTS) 和 Azure，其标识与分配订阅的标识不同。 在过去，仅当 Visual Studio (VS) 订阅已分配到 Microsoft 帐户 (MSA) 时此功能才可用。 我们已经将此功能扩展到 Azure Active Directory (Azure AD) 中的工作或学校帐户。

这不会向其他帐户提供订阅副本；它仅可使用备用帐户访问这两项权益。

对于所有订阅，可以添加“工作或学校帐户”，以便通过该帐户使用需要登录（VS IDE、VSTS 和 Azure）的权益。


### <a name="add-the-alternate-account"></a>添加备用帐户


1. 使用 Microsoft 帐户 (https://my.visualstudio.com) 登录到 Visual Studio 订阅者门户。

2. 转到“订阅”。


   ![添加备用帐户 - 转到 VS 中的订阅](_img/vs-alternate-identity/my-vs-subscriptions.png)

3. 选择“添加备用帐户”。

   ![选择添加备用帐户 ](_img/vs-alternate-identity/choose-add-alternate-account.png)

4. 添加工作或学校帐户。

   ![添加工作或学校帐户](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. 使用工作或学校帐户登录到 Visual Studio Team Services (https://{youraccount}.visualstudio.com)。

   ![使用工作或学校帐户](_img/vs-alternate-identity/sign-in-with-alternate-account.png)

向 Visual Studio 订阅添加备用帐户后，这两个标识可以利用需要使用备用帐户（IDE、VSTS 和 Azure）登录的订阅权益。

## <a name="faq"></a>FAQ

### <a name="q--why-doesnt-vsts-recognize-me-as-a-visual-studio-subscriber"></a>问：为什么 VSTS 不能识别我的 Visual Studio 订阅者身份？

答：使用主要或备用标识登录时，VSTS 应自动识别订阅。 如果没有，可尝试以下操作：

* 检查是否具有[包含 VSTS 权益](vs-vsts.md)的有效 Visual Studio 订阅。

* 确认使用的登录名/标识是 Visual Studio 订阅的主要或备用标识。

* 登录 VSTS 之前至少访问了一次 [Visual Studio 订阅者门户](https://my.visualstudio.com?wt.mc_id=o~msft~docs)。

如果 VSTS 仍然无法识别订阅，请[联系支持部门](https://visualstudio.microsoft.com/team-services/support/)
