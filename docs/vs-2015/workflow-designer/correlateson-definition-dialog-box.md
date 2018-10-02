---
title: CorrelatesOn 定义对话框 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 01af296f4cb7dcaa7785438c54527337c110f609
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471004"
---
# <a name="correlateson-definition-dialog-box"></a>“CorrelatesOn 定义”对话框
**CorrelatesOn**中使用对话框[!INCLUDE[wfd1](../includes/wfd1-md.md)]编辑<xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>属性<xref:System.ServiceModel.Activities.Receive>活动。 [!INCLUDE[crdefault](../includes/crdefault-md.md)] [接收](../workflow-designer/receive-activity-designer.md)主题。  
  
 <xref:System.ServiceModel.Activities.Receive> 活动之间的关联指定工作流中的不同服务操作如何相互连接。  
  
 下表介绍的用户界面 (UI) 元素**CorrelatesOn**对话框。  
  
|UI 元素|描述|  
|----------------|-----------------|  
|**CorrelatesWith**|用于将消息路由到相应工作流实例的 <xref:System.ServiceModel.Activities.CorrelationHandle>。|  
|**XPath 查询**|包含用于从传入消息中提取相关数据的查询的键/值对。 它对应于 <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> 属性。 XPath 查询包含在 <xref:System.ServiceModel.MessageQuerySet> 对象中。|  
  
## <a name="to-launch-the-correlateson-dialog-box"></a>启动“CorrelatesOn”对话框  
 **接收**活动设计器可以从拖动**工具箱**拖放到[!INCLUDE[wfd2](../includes/wfd2-md.md)]图面上任何位置通常放置活动的。 这将创建具有 Receive 的默认 <xref:System.ServiceModel.Activities.Receive> 的 <xref:System.Activities.Activity.DisplayName%2A> 活动。 选择**接收**活动设计器并单击 （集合） 文本旁的省略号按钮**CorrelatesOn**属性在属性网格中的**CorrelatesOn 定义**对话框出现。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Activities.Receive>   
 [添加相关初始值设定项对话框](../workflow-designer/add-correlationinitializers-dialog-box.md)   
 [添加关联对话框](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)   
 [“初始化相关”对话框](../workflow-designer/initialize-correlation-dialog-box.md)