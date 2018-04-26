---
title: 工作流设计器的内容定义对话框
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f20a17cf7e01eafc75263bd2753d686908574752
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="content-definition-dialog-box"></a>“内容定义”对话框

**内容定义**对话框中使用 Windows 工作流设计器中，来配置**内容**属性<xref:System.ServiceModel.Activities.Send>， <xref:System.ServiceModel.Activities.Receive>， <xref:System.ServiceModel.Activities.SendReply>，和<xref:System.ServiceModel.Activities.ReceiveReply>活动。 有关使用此框的活动设计器的详细信息，请参阅[发送](../workflow-designer/send-activity-designer.md)，[接收](../workflow-designer/receive-activity-designer.md)， [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)，和[SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)主题。

下表描述的用户界面 (UI) 元素**初始化相关**对话框中：

|UI 元素|描述|
|----------------|-----------------|
|**消息**|指定的消息内容替换**消息数据**表达式文本框和通过使用类型**消息类型**下拉列表框。 默认情况下，**内容定义**使用<xref:System.ServiceModel.Activities.ReceiveMessageContent>，它应<xref:System.ServiceModel.Channels.Message>或消息协定中的工作流服务定义的类型。|
|**参数**|单击**参数**单选按钮以使用<xref:System.ServiceModel.Activities.ReceiveParametersContent>，这应为数据协定。 使用数据网格设置 <xref:System.Activities.OutArgument> 键/值对的泛型集合，这些键/值对的值将赋给当前工作流中的可变参数。|

**内容定义**对话框由**发送**，**接收**， **ReceiveAndSendReply**，和**SendAndReceiveReply**设计器。 在任何情况下访问它们的方式都相同，此处使用“Receive”设计器来演示该过程。

**接收**活动设计器可以拖动从**工具箱**和放置到工作流设计器图面，只要通常放置活动的。 这将创建具有 Receive 的默认 <xref:System.ServiceModel.Activities.Receive> 的 <xref:System.Activities.Activity.DisplayName%2A> 活动。 选择**接收**活动设计器，然后单击省略号按钮 （内容） 文本旁**内容**属性在属性网格**内容定义**对话框出现。

可以在指定的内容**消息**部分以了解<xref:System.ServiceModel.Activities.ReceiveMessageContent>活动或**参数**部分以了解<xref:System.ServiceModel.Activities.ReceiveParametersContent>活动。

## <a name="see-also"></a>请参阅

- [工作流设计器 UI 帮助](../workflow-designer/workflow-designer-ui-help.md)