---
title: 工作流设计器的初始化相关对话框
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- InitializeCorrelation.UI
ms.assetid: 2a0a1cd3-7b9e-493e-9264-fcf85289ffcf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: edfdef1c1f946e2c5f677d0ff1578a40ea7bcd8f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49906229"
---
# <a name="initialize-correlation-dialog-box"></a>“初始化相关”对话框

**初始化相关**对话框中使用工作流设计器中，若要编辑<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>属性的<xref:System.ServiceModel.Activities.InitializeCorrelation>活动。 有关详细信息，请参阅[InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)。

下表介绍的用户界面 (UI) 元素**初始化相关**对话框：

|UI 元素|描述|
|-|-----------------|
|**关联**|要初始化的相关的 <xref:System.ServiceModel.Activities.CorrelationHandle>。|
|**在初始化**|一个键/值对，包含要初始化的数据。 此值对应于<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>属性。 有效的键/值对的一个示例是名为"OrderID"与名为 OrderID 的变量配合使用的密钥。|

## <a name="to-launch-the-initialize-correlation-dialog-box"></a>启动“初始化相关”对话框

单击**视图**上**InitializeCorrelation**活动设计器或选择<xref:System.ServiceModel.Activities.InitializeCorrelation>工作流设计器中的活动。 然后，单击旁边的省略号按钮<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>属性网格中的属性。

## <a name="see-also"></a>请参阅

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)