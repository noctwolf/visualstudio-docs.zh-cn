---
title: "针对 Visual Studio 的 R 工具的 linting R 代码 | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
f1_keywords: vs.toolsoptionspages.text_editor.r.lint
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: data-science
ms.openlocfilehash: 76f4ceb040e62e4ebac46e8a791f5dac0d73aff5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="linting-r-code-in-visual-studio"></a>Visual Studio 中的 linting R 代码

Linting 进程用于分析代码，揭示代码文件中的潜在错误、格式设置问题和他干扰（例如虚假空白）。 Linting 还可帮助支持特定代码约定（例如如何命名标识符），这在团队和其他协作环境中非常有用。

针对 Visual Studio 的 R 工具 (RTVS) 提供适用于 R 的内置 linting，可通过多个选项控制其行为。 可在“工具”>“选项”>“文本编辑器”>”R”>”Lint”中找到这些选项。

默认情况下禁用 linting。 要启用 linting，请将“全部”>“启用 lint”选项设置为 true。 本主题中后面的部分介绍所有其他 linting 选项：

启用后，在编辑器中键入时会应用 linting。 以绿色波浪线指示问题。 例如，在下图中，RTVS 已识别六个 linting 问题，包括使用 `=` 而不是 `<-` 进行赋值、函数参数周围缺少空格、使用 Pascal 拼写法和大写标识符，以及使用分号。 将鼠标悬停在问题上可查看问题描述。

![用于 R 代码的 linting 的示例](media/linting-01.png)

## <a name="assignment-group"></a>赋值组

| 选项 | 默认值 | Linting 效果 |
| --- | --- | --- |
| 执行 \<- | `True` | 标识 `<-` 何时未用于赋值。 |

## <a name="naming-group"></a>命名组

这些选项标记使用不同命名约定的标识符：

| 选项 | 默认值 | Linting 效果 |
| --- | --- | --- |
| 标记 camelCase | `False` | 标记使用 camelCase 的标识符。 |
| 标记长名称 | `False` | 标记名称长度超过“最大名称长度”设置的标识符。 |
| 标记多个点 | `True` | 标记使用多个点的标识符。 |
| 标记 PascalCase | `True` | 标记使用 PascalCase 的标识符。 |
| 标记 snake_case | `False` | 标记使用下划线的标识符。 |
| 标记大写 | `True` | 标记全部使用大写的标识符。 |
| 最大名称长度 | 32 | 应用“标记长名称”设置的长度。 |

## <a name="spacing-group"></a>空格组

这些选项默认情况下均设置为 `True`，用于控制 linter 识别空格问题的位置：函数名称后、逗号前后、运算符前后、左右大括号位置、( 前和 () 内。

## <a name="statements-group"></a>语句组

| 选项 | 默认值 | Linting 效果 |
| --- | --- | --- |
| 多种 | `True` | 标识多个语句位于同一行的情况。 |
| 分号 | `True` | 标识使用分号。 |

## <a name="text-group"></a>文本组

| 选项 | 默认值 | Linting 效果 |
| --- | --- | --- |
| 行长度限制 | `False` | 设置 linter 标记行是的长度是否大于“最大行长度”选项。 |
| 最大行长度 | 80 | 设置“行长度限制”选项应用的行长度。 |

## <a name="whitespace-group"></a>空白组

这些选项默认状态下均设置为 `True`，用于控制 linter 识别空白问题的位置：使用制表符、使用双引号、尾随空行和尾随空白。