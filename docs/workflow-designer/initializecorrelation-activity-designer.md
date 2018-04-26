---
title: 工作流设计器-InitializeCorrelation 活动设计器
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.InitializeCorrelation.UI
ms.assetid: 4c54f34c-ee84-42a6-abb0-ec260c1ccb76
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 24d319af36b5d07661213edb3cff48d376bd3736
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="initializecorrelation-activity-designer"></a>InitializeCorrelation 活动设计器

**InitializeCorrelation**活动设计器用于创建和配置<xref:System.ServiceModel.Activities.InitializeCorrelation>用于发送或接收其之前的消息之间建立相关的活动。

## <a name="the-initializecorrelation-activity"></a>InitializeCorrelation 活动

<xref:System.ServiceModel.Activities.InitializeCorrelation> 活动用于在不发送或接收消息的情况下初始化相关。 通常，相关是在发送或接收消息时初始化的。 如果必须在发送或接收消息前建立相关，请使用 <xref:System.ServiceModel.Activities.InitializeCorrelation> 来初始化该相关。

### <a name="using-the-initializecorrelation-activity-designer"></a>使用 InitializeCorrelation 活动设计器
 **InitializeCorrelation**在找不到活动设计器**消息**类别**工具箱**，通过单击访问的哪一**工具箱**工作流设计器上的选项卡 (或者，选择**工具栏**从**视图**菜单或 CTRL + ALT + X。)

 **InitializeCorrelation**活动设计器可以拖动从**工具箱**和放置到工作流设计器图面。 这将创建<xref:System.ServiceModel.Activities.InitializeCorrelation>默认值的活动<xref:System.Activities.Activity.DisplayName%2A>的 InitializeCorrelation.The<xref:System.Activities.Activity.DisplayName%2A>可以在的标头中编辑**InitializeCorrelation**活动设计器中或在**DisplayName**框**属性**窗口。

 <xref:System.ServiceModel.Activities.CorrelationHandle>可以是指定在**相关**字段**属性**上的窗口**InitializeCorrelation**活动设计器图面。

 单击省略号按钮，除了**CorrelationData**字段**属性**窗口或上的"视图 …"提示文本**InitializeCorrelation**活动设计器图面显示**初始化相关**对话框中，你可以在其中指定相关句柄和用于对其进行初始化的键 / 值对。 有关使用此对话框中的详细信息，请参阅[类型集合编辑器对话框](../workflow-designer/type-collection-editor-dialog-box.md)主题。

### <a name="the-initializecorrelation-properties"></a>InitializeCorrelation 属性
 下表列出 <xref:System.ServiceModel.Activities.InitializeCorrelation> 属性并说明如何在设计器中使用它们。 可以在中编辑这些属性**属性**窗口或工作流设计器图面上。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.InitializeCorrelation> 活动的友好名称。 默认值为 InitializeCorrelation。<br /><br /> 虽然对友好 <xref:System.Activities.Activity.DisplayName%2A> 使用非默认值不是绝对必需的，但最好使用非默认值。|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.Correlation%2A>|False|用于关联相关中的工作流活动的 <xref:System.ServiceModel.Activities.CorrelationHandle>。|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>|False|将消息与工作流实例相关联的相关数据的字典。<br /><br /> 使用**初始化相关**对话框配置<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>。 有关使用此对话框中，请参阅[类型集合编辑器对话框](../workflow-designer/type-collection-editor-dialog-box.md)主题。|

## <a name="see-also"></a>请参阅

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [接收](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [发送](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)