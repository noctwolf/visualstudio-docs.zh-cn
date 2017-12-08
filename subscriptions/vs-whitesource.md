---
title: "WhiteSource Bolt 权益"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: "了解如何激活 Visual Studio 订阅中包含的 WhiteSource Bolt 订阅。"
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: c1976d9eaa6ef18978a9e9d5453c3080741223d5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
#  <a name="activating-the-whitesource-bolt-benefit-in-visual-studio-subscriptions"></a>激活 Visual Studio 订阅中的 WhiteSource Bolt 权益

查找和修复开源漏洞，在内部版本中生成所有开源组件的综合清单和许可报告。  企业订阅包含六个月的免费订阅。 

1.  要使用 WhiteSource Bolt 权益，请单击权益磁贴底部的“获取代码”链接。    

![WhiteSource 权益磁贴](_img\vs-whitesource\vs-whitesource-tile.png)

2.  你将收到一条显示激活代码的通知。  将代码复制到剪贴板，然后单击“激活”。 

![WhiteSource 权益代码 ](_img\vs-whitesource\vs-whitesource-code.png)

3.  在 WhiteSource 网页上，单击“激活”按钮，或向下滚动到该页面的“激活帐户”部分。  

![激活 WhiteSource 权益](_img\vs-whitesource\vs-whitesource-activate-page-cropped.png)

4.  该页面的“激活帐户”部分将引导你完成以下四个步骤：
- 从 Microsoft Visual Studio 商城[安装](https://marketplace.visualstudio.com/items?itemName=whitesource.ws-bolt) WhiteSource Bolt 扩展。 如果没有安装扩展的权限，请访问[此页](https://www.visualstudio.com/en-us/docs/marketplace/get-vsts-extensions#request)。

    如果使用的是 VSTS，请单击绿色的“安装”按钮；如果使用的是 Team Foundation Server，请单击“下载”按钮。  此处以使用 VSTS 为例。 

![WhiteSource 权益安装扩展](_img\vs-whitesource\vs-whitesource-download-install.png)

- 接下来，选择想要使用的 VSTS 帐户，然后单击“确定”。  （如果尚未设置 VSTS，请访问[权益](https://my.visualstudio.com/benefits)页并激活 VSTS 权益。）

![WhiteSource 权益确认帐户](_img\vs-whitesource\vs-whitesource-confirm-account.png)

- 你会收到一条确认信息，指示该扩展已安装并可以使用。  单击“开始”返回 WhiteSource Bolt 页面，然后继续。  

![WhiteSource 权益安装完毕](_img\vs-whitesource\vs-whitesource-install-complete.png)

5.  打开 Visual Studio Team Services (VSTS) 项目仪表板，单击“生成和发布”菜单，然后选择“WhiteSource Bolt”。

![WhiteSource 权益添加扩展](_img\vs-whitesource\vs-whitesource-installed-cropped.png)

6. 粘贴 WhiteSource Bolt 权益磁贴中的激活代码，然后单击“激活”。 一个激活代码只能激活一个项目。 

![WhiteSource 权益激活代码](_img\vs-whitesource\vs-whitesource-activate-code-cropped.png)

7.  激活现已完成，订阅还剩 180 天。 
8.  在生成步骤中需要添加 WhiteSource Bolt 扩展。  [WhiteSource Bolt 页](https://www.whitesourcesoftware.com/whitesource_bolt_visualstudio_2017/#activate)中提供了一个视频介绍如何操作。  
9. 运行生成后，将自动产生以下完整报告和仪表板：
- 安全漏洞仪表板
- 安全漏洞报告
- 过时的库报表
- 许可证风险和符合性仪表板
- 清单报告
