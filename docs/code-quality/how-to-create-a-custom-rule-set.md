---
title: 创建 Visual Studio 中设置的自定义代码分析规则
ms.date: 04/04/2018
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 727c11e24eb3409de89fe211c6a37691dfec298c
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204110"
---
# <a name="customize-a-rule-set"></a>自定义规则集

可以创建自定义规则集以满足代码分析的特定项目需求。

## <a name="create-a-custom-rule-set"></a>创建自定义规则集

若要创建自定义规则集，则可以打开所设置的内置规则**规则集编辑器**。 在这里，您可以添加或删除的特定规则，并且你可以更改时执行的操作违反规则&mdash;例如，显示一条警告或错误。

1. 在中**解决方案资源管理器**，右键单击项目，然后选择**属性**。

2. 上**属性**页中，选择**代码分析**选项卡。

3. 在中**运行此规则集**下拉列表中，执行下列任一操作：

    - 选择想要自定义的规则集。

     \- 或 -

    - 选择**\<浏览...>** 指定的现有规则集不在列表中。

4. 选择**打开**若要在规则集编辑器中显示的规则。

此外可以创建新的规则集文件从**新的文件**对话框：

1. 选择**文件** > **新建** > **文件**，或按**Ctrl**+**N**.

2. 在**新的文件**对话框中，选择**常规**左边的类别，然后选择**代码分析规则集**。

3. 选择“打开” 。

   新 *.ruleset*规则集编辑器中打开文件。

### <a name="create-a-custom-rule-set-from-multiple-rule-sets"></a>创建自定义规则集从多个规则集

1. 在解决方案资源管理器，右键单击项目，然后选择**属性**。

2. 上**属性**页中，选择**代码分析**选项卡。

3. 选择**\<选择多个规则集...>** 从**运行此规则集**。

4. 在中**添加或删除规则集**对话框中，选择规则集你想要包括在新的规则集。

   ![添加或删除规则集对话框](media/add-remove-rule-sets.png)

5. 选择**另存为**，输入的名称 *.ruleset*文件，并选择**保存**。

   中选择新的规则集**运行此规则集**列表。

6. 选择**打开**以打开新的规则集编辑器中设置的规则。

## <a name="name-and-description"></a>名称和描述

若要更改编辑器中打开的规则集的显示名称，打开**属性**通过选择窗口**视图** > **属性窗口**菜单栏上。 输入中的显示名称**名称**框。 您还可以输入规则集的说明。

## <a name="next-steps"></a>后续步骤

现在，已设置的规则下, 一步是自定义的规则，通过添加或删除规则，或修改规则冲突的严重性。

> [!div class="nextstepaction"]
> [修改规则集编辑器中的规则](../code-quality/working-in-the-code-analysis-rule-set-editor.md)

## <a name="see-also"></a>请参阅

- [如何：配置托管代码项目的代码分析](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)
- [代码分析规则集参考](../code-quality/rule-set-reference.md)