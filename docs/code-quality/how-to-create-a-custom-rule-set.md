---
title: 创建自定义代码分析规则在 Visual Studio 中设置 |Microsoft 文档
ms.date: 04/04/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.addremoverulesets
helpviewer_keywords:
- Development Edition, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 57800f36c3a81e021c1fb40bab1c07bbed3e7f9d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="custom-rule-sets"></a>自定义规则集

你可以创建自定义*规则集*为满足特定的项目代码分析需求。

## <a name="create-a-custom-rule-set"></a>创建自定义规则集

若要创建自定义规则集，你可以打开所设置的内置规则**规则集编辑器**。 在这里，你可以添加或删除特定规则，并且你可以更改违反规则时发生的操作&mdash;例如，显示一条警告或错误。

1. 在**解决方案资源管理器**，右键单击项目，然后选择**属性**。

2. 上**属性**页，选择**代码分析**选项卡。

3. 在**运行此规则集**下拉列表中，执行下列其中一项：

    - 选择你想要自定义规则集。

     \- 或 -

    - 选择**\<浏览 … >**可以指定现有规则集不是在列表中。

4. 选择**打开**若要在规则集编辑器中显示的规则。

你还可以创建新的规则集文件从**新文件**对话框：

1. 选择**文件** > **新建** > **文件**，或按**Ctrl**+**N**.

2. 在**新文件**对话框中，选择**常规**类别在左侧，然后选择**代码分析规则集**。

3. 选择“打开” 。

   新*.ruleset*规则集编辑器中打开文件。

### <a name="create-a-custom-rule-set-from-multiple-rule-sets"></a>创建自定义规则集来自多个规则集

1. 在解决方案资源管理器，右键单击项目，然后选择**属性**。

2. 上**属性**页，选择**代码分析**选项卡。

3. 选择**\<选择多个规则集...>**从**运行此规则集**。

4. 在**添加或移除规则集**对话框中，选择规则集你想要包括在新的规则集。

   ![添加或删除规则设置对话框](media/add-remove-rule-sets.png)

5. 选择**另存为**，输入的名称*.ruleset*文件，，然后选择**保存**。

   在中选择新的规则集**运行此规则集**列表。

6. 选择**打开**以打开新的规则在规则集编辑器中设置。

## <a name="name-and-description"></a>名称和描述

若要更改编辑器中打开的规则集的显示名称，打开**属性**窗口，通过选择**视图** > **属性窗口**菜单栏上。 输入中的显示名称**名称**框。 你也可以输入规则集的说明。

## <a name="next-steps"></a>后续步骤

现在，你已设置的规则下, 一步是通过添加或移除规则时，或修改的规则冲突的严重性自定义规则。

> [!div class="nextstepaction"]
> [修改在规则集编辑器中的规则](../code-quality/working-in-the-code-analysis-rule-set-editor.md)

## <a name="see-also"></a>请参阅

- [如何：配置托管代码项目的代码分析](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)
- [代码分析规则集参考](../code-quality/rule-set-reference.md)