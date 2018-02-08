---
title: "如何重新发送来自 VLSC 的订阅分配电子邮件 | Microsoft 文档"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 12/29/2017
Ms.topic: Get-Started-Article
Description: Learn how to resend the subscription assignment to a subscriber from within VLSC
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 7162435044a578a94249774305f2c6b8b6438219
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-resend-subscription-assignment-emails-from-vlsc"></a>如何重新发送来自 VLSC 的订阅分配电子邮件：

当订阅已分配给 VLSC 中的订阅者且订阅者请求重新发送分配电子邮件时，你可通过编辑订阅者的电子邮件信息，然后将其更改回原始地址来完成此操作。 这将自动触发分配电子邮件的重新发送。

请按照以下说明重新发送分配电子邮件：


1. 访问“批量许可服务中心”(VLSC) 并登录。
2. 从 VLSC 管理页中，单击“订阅”，然后单击“Visual Studio 订阅”。
3. 单击与 Visual Studio 订阅相关联的“协议编号”。
4. 单击“搜索”栏上的向下箭头。  
5. 使用“电子邮件地址”字段搜索订阅者。
6. 从结果列表中，单击订阅者的“姓氏”。
7. 单击“编辑”。
8. 对订阅进行编辑。 所做的具体更改并不重要 - 只是需要更改一下。  例如，从订阅者的电子邮件地址中删除一个字符 - 从 .com 中删除“m”。单击“保存”按钮
9. 保存信息后，再次单击“编辑”按钮，然后更正邮件中缺少的字符。 单击“保存”。
   
这将会使 VLSC 识别到订阅上已发生的更改，并将分配电子邮件重新发送到门户上列出的电子邮件。 

> [!NOTE]
> - 新分配的订阅会自动生成分配电子邮件。 只有当用户请求新分配电子邮件通知或出于某种原因未发送通知时，才必须进行上述操作。
> - 此过程不需要重新发送通过 https://manage.visualstudio.com 分配的订阅分配电子邮件。若要重新发送分配电子邮件到门户中的订阅者，只需选择订阅者，然后单击订阅者列表顶部的“重新发送”按钮。  