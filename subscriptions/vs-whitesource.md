---
title: WhiteSource Bolt 权益 | Microsoft 文档
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/11/2017
ms.topic: Get-Started-Article
description: 了解如何激活 Visual Studio 订阅中包含的 WhiteSource Bolt 订阅。
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 981d6a655a203a7d44728fa7d12761fba2918d76
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49935768"
---
#  <a name="whitesource-bolt-in-visual-studio-subscriptions"></a>Visual Studio 订阅中的 WhiteSource Bolt

查找和修复开源漏洞，在内部版本中生成所有开源组件的综合清单和许可报告。 一些 Visual Studio 订阅包括 6 个月免费访问期限。

## <a name="activation-steps"></a>激活步骤

1. 若要激活 WhiteSource Bolt 权益，请登录到 [https://my.visualstudio.com/benefits](https://my.visualstudio.com/benefits?wt.mc_id=o~msft~docs)。

2. 在“工具”部分中找到“WhiteSource Bolt”磁贴，然后单击“权益”磁贴底部的“获取代码”链接。
   > [!div class="mx-imgBorder"]
   > ![WhiteSource 权益磁贴](_img/vs-whitesource/vs-whitesource-tile.png)

3. 你将收到一条显示激活代码的通知。  将代码复制到剪贴板，然后单击“激活”。
   > [!div class="mx-imgBorder"]
   > ![WhiteSource 权益代码](_img/vs-whitesource/vs-whitesource-code.png)

4. 在 WhiteSource 网页上，单击“激活”按钮，或向下滚动到该页面的“激活帐户”部分。
   > [!div class="mx-imgBorder"]
   > ![激活 WhiteSource 权益](_img/vs-whitesource/vs-whitesource-activate-page-cropped.png)

5. 该页面的“激活帐户”部分将引导你完成以下四个步骤：

   - 从 Microsoft Visual Studio Marketplace [安装](https://marketplace.visualstudio.com/items?itemName=whitesource.ws-bolt) WhiteSource Bolt 扩展。 如果无权安装扩展，请参阅[安装适用于 Azure DevOps Services 的免费扩展](/azure/devops/marketplace/install-vsts-extension?view=vsts)。


~~~
Click the green **Install** button if you are using Azure DevOps Services, or the **Download** button for Team Foundation Server.  For this example, we will use Azure DevOps Services.
> [!div class="mx-imgBorder"]
> ![WhiteSource Benefit Install Extension](_img\vs-whitesource\vs-whitesource-download-install.png)

- Next, select the Azure DevOps organization you want to use and click **Confirm**.  (If you have not yet set up Azure DevOps Services, visit the [Benefits](https://my.visualstudio.com/benefits) page and activate your Azure DevOps Services benefit.)

> [!div class="mx-imgBorder"]
> ![WhiteSource Benefit Confirm Account](_img\vs-whitesource\vs-whitesource-confirm-account.png)

- You’ll receive a confirmation that the extension is installed and ready to use.  Click **Get started** to return to the WhiteSource Bolt page and continue.
> [!div class="mx-imgBorder"]
> ![WhiteSource Benefit Install Complete](_img\vs-whitesource\vs-whitesource-install-complete.png)
~~~

5. 打开 Azure DevOps 项目仪表板，单击“Azure Pipelines”菜单，然后选择“WhiteSource Bolt”。
   > [!div class="mx-imgBorder"]
   > ![WhiteSource 权益添加扩展](_img/vs-whitesource/vs-whitesource-installed-cropped.png)

6. 粘贴 WhiteSource Bolt 权益磁贴中的激活代码，然后单击“激活”。 一个激活代码只能激活一个项目。
   > [!div class="mx-imgBorder"]
   > ![WhiteSource 权益激活代码](_img/vs-whitesource/vs-whitesource-activate-code-cropped.png)

7. 激活现已完成，订阅还剩 180 天。

8. 在生成步骤中需要添加 WhiteSource Bolt 扩展。  [WhiteSource Bolt 页](https://www.whitesourcesoftware.com/whitesource_bolt_visualstudio_2017/#activate)中提供了一个视频介绍如何操作。

9. 运行生成后，将自动产生以下完整报告和仪表板：
    - 安全漏洞仪表板
    - 安全漏洞报告
    - 过时的库报表
    - 许可证风险和符合性仪表板
    - 清单报告

## <a name="eligibility"></a>资格

| 订阅级别                                                 |     信道                                            | 好处                                                          | 是否续订？    |
|--------------------------------------------------------------------|---------------------------------------------------------|------------------------------------------------------------------|---------------|
| Visual Studio Enterprise（标准、年度云）   | VL、Azure、零售、所选 NFR<sup>1</sup> | 6 个月       |  是          |
| Visual Studio Professional（标准、年度云） | VL、Azure、零售                                       | 不可用                                                           |NA         |
| Visual Studio Test Professional（标准）                         | VL、零售                                              | 不可用                                             |  NA         |
| MSDN 平台（标准）                                          | VL、零售                                              | 不可用                                              | NA         |
| Visual Studio Dev Essentials | NA  | 不可用 |NA |
| Visual Studio Enterprise、Visual Studio Professional（月度云） | Azure                                       | 不可用                                                           |NA|

<sup>1</sup> 包括：Microsoft 合作伙伴网络 (Enterprise)。不包括：其他的不得转售 (NFR)、Visual Studio 行业合作伙伴 (VSIP)、FTE、MCT 软件和服务开发人员、BizSpark、Imagine、Microsoft 最有价值专家 (MVP)、区域总监 (RD)、MCT 软件和服务、Microsoft 合作伙伴网络（专业）。

无法确定正在使用哪些订阅？  连接到 [https://my.visualstudio.com/subscriptions](https://my.visualstudio.com/subscriptions?wt.mc_id=o~msft~docs)，查看分配给电子邮件地址的所有订阅。 如果没有看到所有订阅，则可能是有一个或多个订阅分配给了不同的电子邮件地址。  你需要使用其他电子邮件地址登录来查看那些订阅。

## <a name="support-resources"></a>支持资源

-  需要 WhiteSource Bolt 帮助？  在 https://www.whitesourcesoftware.com/vse_whitesource_bolt/ 与 WhiteSource Bolt 代表实时聊天
-  有关 Visual Studio 订阅的销售、订阅、帐户和账单的帮助，请与 Visual Studio [订阅支持](https://visualstudio.microsoft.com/subscriptions/support/)联系。
-  对有关 Visual Studio IDE、Azure DevOps Services 或其他 Visual Studio 产品或服务有疑问？  请访问 [Visual Studio 支持](https://visualstudio.microsoft.com/support/)。