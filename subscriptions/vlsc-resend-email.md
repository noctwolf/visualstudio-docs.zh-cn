---
title: "Visual Studio 订阅 - 从 VLSC 重新发送分配电子邮件"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 1/23/2018
Ms.topic: Get-Started-Article
Description: Learn how to resend subscription assignment emails from within VLSC
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 338ae08ee1f3e6a819a1faea7bd095c9acd8ecd2
ms.sourcegitcommit: e5bd950df79175a96fe62b3d4b17a3ef536ec4c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2018
---
# <a name="how-to-resend-subscription-assignment-emails-from-within-volume-license-service-center-vlsc"></a>如何从批量许可服务中心 (VLSC) 重新发送订阅分配电子邮件

有时，向其分配了订阅的订阅者将要求管理员重新发送其订阅分配通知电子邮件。  在新的订阅管理门户 (https://manage.visualstudio.com) 中，这一过程非常简单。  但是，如果组织仍在使用批量许可服务中心 (VLSC)，则没有用于自动重新发送通知电子邮件的功能。  

若要从 VLSC 重新发送分配通知电子邮件，管理员需要使用以下解决方法：

## <a name="resending-the-assignment-email"></a>重新发送分配电子邮件：

为了使 VLSC 生成新的通知，需要对订阅者的电子邮件信息进行一次编辑，然后将其更改回同一事务上的原始电子邮件。 这将导致 VLSC 做出反应，就好像已分配新的订阅，并再次发送分配电子邮件。

1.  访问[批量许可服务中心 (VLSC)](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 并登录。
2.  单击“订阅”选项卡，选择“Visual Studio 订阅”。
3.  单击与 Visual Studio 订阅相关联的“协议编号”。
4.  单击“搜索”栏上的向下箭头。 
5.  使用“电子邮件地址”字段搜索订阅者。
6.  在搜索结果中找到订阅者，并单击姓氏。 
7.  单击“编辑” 。
8.  对订阅进行编辑。 例如，从订阅者的电子邮件地址中删除字符。 单击“保存”按钮。
9.  保存信息后，再次单击“编辑”，恢复刚刚所作的更改，然后单击“保存”。  

这将导致订阅被视为新的分配，并会向订阅者重新发送分配通知电子邮件。  