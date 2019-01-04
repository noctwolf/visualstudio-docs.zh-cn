---
title: 工作流设计器的初始化相关对话框
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- InitializeCorrelation.UI
ms.assetid: 2a0a1cd3-7b9e-493e-9264-fcf85289ffcf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51f001e053b0c2fdfe892175b00ed3f39dc6f1b4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53829756"
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