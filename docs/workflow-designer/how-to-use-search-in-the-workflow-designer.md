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
ms.openlocfilehash: 4b5dfdd4b4d05969406f93801bcf87880949e41a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-search-in-the-workflow-designer"></a>如何：在工作流设计器中使用搜索

为方便创建更大、更复杂的工作流，可在工作流设计器中使用搜索来按关键字查找项。 请注意，设计器不支持替换。 搜索将在设计器中查找以下内容：

## <a name="quick-find"></a>快速查找

快速查找设计器中查找以下：

-   <xref:System.Activities.Activity> 对象、<xref:System.Activities.Statements.FlowNode> 对象、<xref:System.Activities.Statements.State> 对象、转换以及其他自定义流控制项的属性。

-   变量

-   参数

-   表达式

### <a name="using-quick-find"></a>使用“快速查找”

1.  工作流设计器中打开，以按**Ctrl + F**，或选择**编辑**，**查找和替换**，**快速查找**。

2.  输入搜索项插入到**查找内容**文本框中，单击**查找下一个**。

3.  将在当前工作流中查找搜索词。 下面的屏幕快照显示了位于设计器中的活动显示名称。

     ![在工作流设计器中搜索结果](../workflow-designer/media/designersearch.png "DesignerSearch")

## <a name="find-in-files"></a>在文件中查找

使用“在文件中查找”将找到工作流文件（包括 XAML 文件）中的字符串。

### <a name="using-find-in-files"></a>使用“在文件中查找”

1.  在 Visual Studio 中，按**Ctrl + Shift + F**，或选择**编辑**，**查找和替换**，**在文件中查找**

2.  输入搜索项插入**查找内容**文本框中，单击**查找全部**

3.  查找的结果将显示在 Visual Studio**查找结果**视图。 双击某个结果项将导航到包含工作流设计器中的匹配项的活动。