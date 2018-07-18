---
title: 如何：在工作流设计器中使用搜索
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: f42d3115-2ed2-4941-8f1e-92dac41c30fa
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 3e8e44586f6b0f2f8aea5ab13eb27886d7b3a6e8
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757963"
---
# <a name="how-to-use-search-in-the-workflow-designer"></a>如何：在工作流设计器中使用搜索

为方便创建更大、 更复杂的工作流，可以按关键字查找项在工作流设计器中进行搜索。 请注意，设计器不支持替换。

## <a name="quick-find"></a>快速查找

快速查找设计器中查找以下：

-   <xref:System.Activities.Activity> 对象、<xref:System.Activities.Statements.FlowNode> 对象、<xref:System.Activities.Statements.State> 对象、转换以及其他自定义流控制项的属性。

-   变量

-   参数

-   表达式

### <a name="use-quick-find"></a>使用快速查找

1.  工作流设计器中打开，然后按**Ctrl + F**，或选择**编辑** > **查找和替换** > **快速查找**.

2.  输入到搜索词**查找内容**文本框中，单击**查找下一个**。

3.  搜索字词位于当前工作流中。 下图显示了位于设计器中的活动显示名称：

   ![在工作流设计器中搜索结果](../workflow-designer/media/designersearch.png)

## <a name="find-in-files"></a>在文件中查找

在文件中的查找来定位工作流文件，包括 XAML 文件中的字符串。

### <a name="use-find-in-files"></a>使用查找在文件中

1.  在 Visual Studio 中，按**Ctrl**+**Shift**+**F**，或选择**编辑** >  **查找和替换** > **在文件中查找**。

2.  输入搜索项插入**查找内容**文本框中，单击**查找全部**。

3.  查找结果所示**查找结果**视图。 双击结果项导航到包含工作流设计器中的匹配项的活动。