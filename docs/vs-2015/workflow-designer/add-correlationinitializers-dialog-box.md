---
title: 添加相关初始值设定项对话框 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- AddCorrelationInitializers.UI
ms.assetid: c0517467-d54a-4ee6-aef0-c19b96b6f395
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 4d4d69185bef36ab514c984716cc6606f6068fb4
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49275686"
---
# <a name="add-correlationinitializers-dialog-box"></a>“添加相关初始值设定项”对话框
**添加相关初始值设定项**中使用对话框[!INCLUDE[wfd1](../includes/wfd1-md.md)]若要配置**相关初始值设定项**属性的<xref:System.ServiceModel.Activities.Send>， <xref:System.ServiceModel.Activities.Receive>， <xref:System.ServiceModel.Activities.SendReply>，和<xref:System.ServiceModel.Activities.ReceiveReply>活动。 [!INCLUDE[crabout](../includes/crabout-md.md)] 活动设计器使用此框，请参阅[发送](../workflow-designer/send-activity-designer.md)，[接收](../workflow-designer/receive-activity-designer.md)， [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)，以及[SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)主题。  
  
 使用此对话框指定的集合中的相关初始值设定项可初始化基于查询的上下文、回调上下文或各消息传递活动之间的请求-答复相关性。  
  
 下表介绍的用户界面 (UI) 元素**添加相关初始值设定项**对话框。  
  
|UI 元素|描述|  
|----------------|-----------------|  
|**添加初始值设定项**|单击**添加 initialize**框以将其他初始值设定项添加到集合。|  
|**相关类型**|指定相关初始值设定项的类型。 有四种类型可供选择：<br /><br /> 1.用于指定 <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer> 的回调相关初始值设定项。<br />2.用于指定 <xref:System.ServiceModel.Activities.CorrelationInitializer> 的上下文相关初始值设定项。<br />3.用于指定 <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> 的请求-答复相关初始值设定项。<br />4.用于指定 <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 的查询相关初始值设定项。<br /><br /> 若要编辑**CorrelationType**<br /><br /> 1.中的特定行的选项卡**添加初始值设定项**DataGrid。<br />2.按 Ctrl + Tab 将焦点设置到**CorrelationTypeComboBox**<br />3.按 Alt + 向下弹出**组合框**和对其进行编辑。|  
|**XPath 查询**|包含用于从传入和传出消息中提取相关数据的查询的键/值对。 仅当使用 <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 类型时此列表才有效。|  
  
## <a name="to-launch-the-add-correlation-initializers-dialog-box"></a>启动“添加相关初始值设定项”对话框  
 **添加相关初始值设定项**通过使用对话框**发送**，**接收**， **ReceiveAndSendReply**，和**SendAndReceiveReply**设计器。 访问它们是在每个用例和用例涉及类似**接收**设计器是使用此处来演示该过程。  
  
 **接收**活动设计器可以从拖动**工具箱**拖放到[!INCLUDE[wfd2](../includes/wfd2-md.md)]图面上任何位置通常放置活动的。 这将创建具有 Receive 的默认 <xref:System.ServiceModel.Activities.Receive> 的 <xref:System.Activities.Activity.DisplayName%2A> 活动。 选择**接收**活动设计器并单击 （集合） 文本旁的省略号按钮**相关初始值设定项**属性在属性网格中的**添加相关初始值设定项**对话框出现。  
  
## <a name="see-also"></a>请参阅  
 [添加关联对话框](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)   
 [“初始化相关”对话框](../workflow-designer/initialize-correlation-dialog-box.md)