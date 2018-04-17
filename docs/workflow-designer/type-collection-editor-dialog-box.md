---
title: 类型集合编辑器对话框 |Microsoft 文档
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TypeCollectionEditor.UI
ms.assetid: 63cdea6b-bca2-4c06-b8b4-c8faabd40726
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 77de1cdcffc1303a439afe743cdfd52b121779d7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="type-collection-editor-dialog-box"></a>“类型集合编辑器”对话框

**类型集合编辑器**对话框用于添加到已知的类型**发送**和**接收**活动。 此外可以使用此对话框来添加到泛型类型自变量**InvokeMethod**活动。 当用于**发送**和**接收**活动添加已知的类型，**类型集合编辑器**对话框需要类型添加项。 是唯一的。 如果添加了重复的类型，并且通过单击提交了更改**确定**，返回错误消息。 当用于**InvokeMethod**活动添加泛型类型参数时，**类型集合编辑器**对话框允许添加重复的类型。

有关详细信息，请参阅[数据协定已知的类型](/dotnet/framework/wcf/feature-details/data-contract-known-types)。

下表描述的用户界面 (UI) 元素**类型集合**对话框。

|UI 元素|描述|
|----------------|-----------------|
|**类型列表**|已添加或移除的类型的列表。|

## <a name="to-bring-up-the-type-collection-editor-for-the-send-and-receive-activities"></a>为 Send 和 Receive 活动打开“类型集合编辑器”

1.  选择**发送**或**接收**设计视图中的活动。

2.  按**F4**弹出**属性**窗口。

3.  在**属性**窗口中，单击省略号按钮旁边**KnownTypes**属性。

## <a name="to-bring-up-the-type-collection-editor-for-the-invokemethod-activity"></a>为 InvokeMethod 活动打开“类型集合编辑器”

1.  选择**InvokeMethod**设计视图中的活动。

2.  按**F4**弹出**属性**窗口。

3.  在**属性**窗口中，单击省略号按钮旁边**GenericTypeArguments**属性。