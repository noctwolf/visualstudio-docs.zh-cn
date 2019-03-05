---
title: WhiteSource Bolt 权益 | Microsoft 文档
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 12/19/2018
ms.topic: conceptual
description: 了解如何激活 Visual Studio 订阅中包含的 WhiteSource Bolt 订阅。
searchscope: VS Subscription
ms.openlocfilehash: 482f0e5054b1b2ad7ea677b40d5d368004227ec8
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56842190"
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


如果使用的是 Azure DevOps Services，请单击绿色的“安装”按钮；如果使用的是 Team Foundation Server，请单击“下载”按钮。  此示例中，我们将使用 Azure DevOps Services。
> [!div class="mx-imgBorder"]
> ![WhiteSource 权益安装扩展](_img/vs-whitesource/vs-whitesource-download-install.png)

- 接下来，选择要使用的 Azure DevOps 组织，然后单击“确认”。  （如果尚未设置 Azure DevOps Services，请访问[权益](https://my.visualstudio.com/benefits)页面并激活 Azure DevOps Services 权益。）

> [!div class="mx-imgBorder"]
> ![WhiteSource 权益确认帐户](_img/vs-whitesource/vs-whitesource-confirm-account.png)

- 你会收到一条确认信息，指示该扩展已安装并可以使用。  单击“开始”返回 WhiteSource Bolt 页面，然后继续。
> [!div class="mx-imgBorder"]
> ![WhiteSource 权益安装完毕](_img/vs-whitesource/vs-whitesource-install-complete.png)

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
| Visual Studio Enterprise（标准）   | VL、Azure、零售、所选 NFR<sup>1</sup> | 6 个月       |  是          |
| Visual Studio Professional（标准） | VL、Azure、零售                                       | 不可用                                                           |NA         |
| Visual Studio Test Professional（标准）                         | VL、零售                                              | 不可用                                             |  NA         |
| MSDN 平台（标准）                                          | VL、零售                                              | 不可用                                              | NA         |
| Visual Studio Dev Essentials | NA  | 不可用 |NA |
| Visual Studio Enterprise、Visual Studio Professional（月度云） | Azure                                       | 不可用                                                           |NA|

<sup>1</sup>  *包括：Microsoft 合作伙伴网络 (Enterprise)。不包括：其他不得转售 (NFR)、Visual Studio 行业合作伙伴 (VSIP)、FTE、MCT 软件和服务开发人员、BizSpark、Imagine、最有价值专家 (MVP)、区域总监 (RD)、MCT 软件和服务、Microsoft 合作伙伴网络 (Professional)。


> [!NOTE]
> Microsoft 不再在云订阅中提供 Visual Studio Professional 年度订阅和 Visual Studio Enterprise 年度订阅。 现有客户体验以及续订、增加、减少或取消订阅的能力不会发生变化。 我们鼓励新客户访问 [https://visualstudio.microsoft.com/vs/pricing/](https://visualstudio.microsoft.com/vs/pricing/) 以浏览购买 Visual Studio 的不同选项。


无法确定正在使用哪些订阅？  连接到 [https://my.visualstudio.com/subscriptions](https://my.visualstudio.com/subscriptions?wt.mc_id=o~msft~docs)，查看分配给电子邮件地址的所有订阅。 如果没有看到所有订阅，则可能是有一个或多个订阅分配给了不同的电子邮件地址。  你需要使用其他电子邮件地址登录来查看那些订阅。

## <a name="support-resources"></a>支持资源

-  需要 WhiteSource Bolt 帮助？  在 https://www.whitesourcesoftware.com/vse_whitesource_bolt/ 与 WhiteSource Bolt 代表实时聊天
-  有关 Visual Studio 订阅的销售、订阅、帐户和账单的帮助，请与 Visual Studio [订阅支持](https://visualstudio.microsoft.com/subscriptions/support/)联系。
-  对有关 Visual Studio IDE、Azure DevOps Services 或其他 Visual Studio 产品或服务有疑问？  请访问 [Visual Studio 支持](https://visualstudio.microsoft.com/support/)。