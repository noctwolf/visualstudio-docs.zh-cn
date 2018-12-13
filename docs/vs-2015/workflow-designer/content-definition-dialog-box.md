---
title: 内容定义对话框的 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
caps.latest.revision: 3
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 0c0fffed6bbb8d9690f96679d910d5ac4a3b631e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49176108"
---
# <a name="content-definition-dialog-box"></a>“内容定义”对话框
**内容定义**中使用对话框[!INCLUDE[wfd1](../includes/wfd1-md.md)]若要配置**内容**属性的<xref:System.ServiceModel.Activities.Send>， <xref:System.ServiceModel.Activities.Receive>， <xref:System.ServiceModel.Activities.SendReply>，和<xref:System.ServiceModel.Activities.ReceiveReply>活动。 [!INCLUDE[crabout](../includes/crabout-md.md)] 活动设计器使用此框，请参阅[发送](../workflow-designer/send-activity-designer.md)，[接收](../workflow-designer/receive-activity-designer.md)， [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)，以及[SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)主题。  
  
 下表介绍的用户界面 (UI) 元素**初始化相关**对话框。  
  
|UI 元素|描述|  
|----------------|-----------------|  
|**消息**|指定内容的消息**消息数据**表达式文本框中并通过键入**消息类型**下拉列表框。 默认情况下**内容定义**使用<xref:System.ServiceModel.Activities.ReceiveMessageContent>，它应<xref:System.ServiceModel.Channels.Message>或消息协定中的工作流服务定义的类型。|  
|**参数**|单击**参数**单选按钮以使用<xref:System.ServiceModel.Activities.ReceiveParametersContent>，这应为数据协定。 使用数据网格设置 <xref:System.Activities.OutArgument> 键/值对的泛型集合，这些键/值对的值将赋给当前工作流中的可变参数。|  
  
 **内容定义**通过使用对话框**发送**，**接收**， **ReceiveAndSendReply**，和**SendAndReceiveReply**设计器。 在任何情况下访问它们的方式都相同，此处使用“Receive”设计器来演示该过程。  
  
 **接收**活动设计器可以从拖动**工具箱**拖放到[!INCLUDE[wfd2](../includes/wfd2-md.md)]图面上任何位置通常放置活动的。 这将创建具有 Receive 的默认 <xref:System.ServiceModel.Activities.Receive> 的 <xref:System.Activities.Activity.DisplayName%2A> 活动。 选择**接收**活动设计器并单击 （内容） 文本旁的省略号按钮**内容**属性在属性网格中的**内容定义**对话框出现。  
  
 可以在指定的内容**消息**部分，了解<xref:System.ServiceModel.Activities.ReceiveMessageContent>活动中或在**参数**部分<xref:System.ServiceModel.Activities.ReceiveParametersContent>活动。  
  
## <a name="see-also"></a>请参阅  
 [工作流设计器 UI 帮助](../workflow-designer/workflow-designer-ui-help.md)