---
title: Visual Studio 订阅者标识
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 3/15/2018
Ms.topic: Get-Started-Article
Description: How to add an alternate identity for your Visual Studio subscription, to use for VSTS and Azure.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 70bfd305ec35b562fb722fb853016c3df4240ff8
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="identities-for-visual-studio-subscribers"></a>Visual Studio 订阅者标识

激活 Visual Studio 订阅时，我们会将用户激活期间使用的标识（或登录名）与 Visual Studio 订阅关联起来。 这样，就可以在 [Visual Studio 订阅者门户](https://my.visualstudio.com?wt.mc_id=o~msft~docs)、VSTS 和 Azure 中识别出该用户。

在 VSTS 中，我们会在用户每次登录时检查其 Visual Studio 订阅状态，并在其所属的每个帐户中自动授予相应功能。 因为这些功能包含在订阅者权益中，所以在使用链接到 Visual Studio 订阅的身份时，可以将用户添加为任何 VSTS 帐户中的成员。

在 Azure 中，用户激活其[每月 Azure 额度](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/)（一项订阅者权益）时，我们会检查其 Visual Studio 订阅状态。

在 [Visual Studio 订阅者门户](https://my.visualstudio.com?wt.mc_id=o~msft~docs)中，除激活过程中使用的标识外，还可添加备用标识。 现在，如果使用 Microsoft 帐户激活订阅，则可添加备用标识。 通过这种方式，用户还可添加工作或学校帐户（登录 Visual Studio、Office 365 或公司/学校网络时使用的帐户），从而允许用户使用个人帐户和工作或学校帐户访问 VSTS。

## <a name="how-to-add-an-alternate-identity-to-your-visual-studio-subscription"></a>如何向 Visual Studio 订阅添加备用标识

1. 登录到 [Visual Studio 订阅者门户](https://my.visualstudio.com?wt.mc_id=o~msft~docs)。

  > 如果系统要求选择“个人帐户”或“工作或学校帐户”，请选择“个人帐户”（Microsoft 帐户）。
  >
  > 由于 Microsoft 帐户和工作或学校帐户共享相同的电子邮件地址，因此有时候需要进行选择。 尽管两个标识使用相同的电子邮件地址，但它们仍是相互独立的标识，具有不同的配置文件、安全设置和权限。
  >
  > 从 2018 年 3 月 30 日开始，如果电子邮件使用在 Azure Active Directory 中管理的域，则无法再使用该电子邮件创建 Microsoft 帐户。 但仍可使用此电子邮件作为工作帐户登录。

2. 转到“订阅”选项卡。

  ![选择“订阅”](_img/vs-alternate-identity/choose-subscriptions-my-visual-studio-com-portal.png)

3. 在“相关链接”下，转到“添加备用帐户”。

  ![在“相关链接”下，转到“添加备用帐户”](_img/vs-alternate-identity/add-alternate-account-my-visual-studio-com-portal.png)

4. 输入工作或学校帐户，然后选择“添加”。

  ![输入工作或学校帐户](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. 使用工作或学校帐户登录到 VSTS 帐户 (```https://{youraccount}.visualstudio.com```)。 信息传播可能稍有延迟，因此请在 15 分钟后再检查一次。 

## <a name="faq"></a>FAQ

### <a name="q--why-doesnt-vsts-recognize-me-as-a-visual-studio-subscriber"></a>问：为什么 VSTS 不能识别我的 Visual Studio 订阅者身份？
答：使用主要或备用标识登录时，VSTS 应自动识别订阅。 如果没有，可尝试以下操作：

* 检查是否具有[包含 VSTS 权益](vs-vsts.md)的有效 Visual Studio 订阅。

* 确认使用的登录名/标识是 Visual Studio 订阅的主要或备用标识。

* 登录 VSTS 之前至少访问了一次 [Visual Studio 订阅者门户](https://my.visualstudio.com?wt.mc_id=o~msft~docs)。

如果 VSTS 仍然无法识别订阅，请[联系支持部门](https://www.visualstudio.com/team-services/support/)

