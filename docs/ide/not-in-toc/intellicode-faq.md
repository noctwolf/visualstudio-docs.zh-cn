---
title: IntelliCode 问题和解答
ms.date: 07/12/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
ms.openlocfilehash: 79e18778eae231d16cf32c0fa68bcb6f5564b09d
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39079306"
---
# Visual Studio IntelliCode 常见问题解答

感谢关注 Visual Studio IntelliCode！ 此简短的常见问题解答，有望能回答你的一些问题。

## 问： 什么是 Visual Studio IntelliCode？

在 Build 2018 中，Microsoft 宣布推出 Visual Studio IntelliCode，这是一种使用 AI 增强软件开发的新功能。 IntelliCode 有助于开发人员和团队自信地进行编码、更快地发现问题并专注于代码评审。

早期的 IntelliCode 视图展示了它如何通过以下方式增强软件开发过程：

- 提供上下文感知代码完成
- 指导开发人员遵守团队的模式和样式
- 发现难以察觉的代码问题
- 将关注点集中到重要领域，从而专注代码评审

开发人员可在 [https://aka.ms/intellicode](https://aka.ms/intellicode) 上找到详细信息并注册，以获取新闻和将来的个人预览版。

## 问： Visual Studio IntelliCode 为客户提供哪些功能？

Visual Studio IntelliCode 是通过人工智能 (AI) 提供新的工作效率增强功能的一系列功能。

开发人员可以为 Visual Studio 2017 版本 15.7 及更高版本[下载试验扩展](https://go.microsoft.com/fwlink/?linkid=872707)。 该扩展目前提供：

- AI 增强的 IntelliSense，可预测供开发人员使用的最可能正确的 API，而不仅仅是呈现按字母顺序排列的成员列表。 它使用开发人员当前的代码上下文和模式来提供此动态列表。

- 代码样式和格式约定的推理，可通过从代码库动态创建 [.editorconfig 文件](../create-portable-custom-editor-options.md)来定义编码样式和格式，从而帮助保持代码的一致性。 这些约定允许 Visual Studio 提供自动样式和格式修复来清理文档。

我们将在未来几个月中更新具有更多功能的扩展。

## 问： 为什么 EditorConfig 推理会在文件名前加 1？

右键单击并选择“添加”>“新建项”来创建 .editorconfig 文件名时， Visual Studio 可扩展性中的已知问题将导致在该文件名前加上 1。 Visual Studio 中的 .editorconfig 处理器无法识别以这种方式命名的文件。 此问题已在 Visual Studio 2017 版本 15.8 预览版 4 中得到修复，但在此之前，可通过删除“添加新项”对话框中的 1 来解决此问题。

## 问： 为什么未看到我的 EditorConfig 约定生效？
出现此问题有几个常见原因：

- 在 15.8 预览版 3 之前的 Visual Studio 2017 版本中，需要关闭并重新打开所有打开的文档，以查看创建的 EditorConfig 文件中的约定是否生效。 此问题已在 15.8 预览版 3 发布中得到修复。
- 格式设置约定永远不会出现在代码中的“错误列表”或“波形曲线”中。 但是，可使用 Visual Studio 2017 版本 15.8 预览版 3 或更高版本中的新格式文档（Ctrl+K、Ctrl+D）扩展来修复它们

## 问： 为什么格式化文档未修复我的样式约定？
出现此问题有几个常见原因：

- 你使用的版本可能不是 Visual Studio 2017 版本 15.8 预览版 3 或更高版本。 需要使用此版本才能使用扩展的“格式文档”命令为当前文档执行其他代码清理。
- 你可能未选择加入样式修复。 “格式文档”中修复基于约定的问题的扩展功能仅涵盖一组固定的问题。 可在“文本编辑器”>“C#”>“代码样式”>“格式设置”>“常规”>“格式文档设置”（试验）下的“工具”-“选项”中更改要修复的问题。 请注意，默认设置无法修复某些样式约定。 可通过“工具”>“选项”选择加入这些内容。 例如，“应用隐式/显式类型首选项”将运行使用 `var` 的相关样式规则。

## 问： Visual Studio IntelliCode 可推断出哪些 EditorConfig 约定？

目前此功能处于试验阶段，因此尚不支持[代码样式设置引用](../editorconfig-code-style-settings-reference.md)中记录的完整约定集。

IntelliCode 目前可推断出以下约定：

格式设置约定：

-   csharp_space_between_method_declaration_parameter_list_parentheses
-   csharp_space_between_method_declaration_empty_parameter_list_parentheses
-   csharp_space_between_method_call_name_and_opening_parenthesis
-   csharp_space_between_method_call_parameter_list_parentheses
-   csharp_space_between_method_call_empty_parameter_list_parentheses
-   csharp_space_after_keywords_in_control_flow_statements
-   csharp_space_between_parentheses
-   csharp_space_after_cast
-   csharp_space_after_colon_in_inheritance_clause
-   csharp_space_before_colon_in_inheritance_clause
-   csharp_space_around_binary_operators
-   csharp_indent_switch_labels
-   csharp_indent_case_contents
-   csharp_indent_case_contents_when_block
-   csharp_indent_labels
-   csharp_preserve_single_line_blocks
-   csharp_preserve_single_line_statements
-   csharp_new_line_before_open_brace
-   csharp_new_line_before_else
-   csharp_new_line_before_catch
-   csharp_new_line_before_finally
-   csharp_new_line_before_members_in_object_initializers
-   csharp_new_line_before_members_in_anonymous_types
-   csharp_new_line_between_query_expression_clauses

样式约定
-   csharp__new_line_before_catch
-   csharp_new_line_before_else
-   csharp_new_line_before_members_in_anonymous_types
-   csharp_new_line_before_members_in_object_initializers
-   csharp_new_line_before_finally_style
-   csharp_new_line_between_query_expression_clauses
-   csharp_prefer_braces_style
-   csharp_preferred_modifier_order_style
-   csharp_prefer_simple_default_expression
-   csharp_preserve_single_line_blocks
-   csharp_space_after_cast
-   csharp_space_after_keywords_in_control_flow_statements
-   csharp_space_between_method_call_parameter_list_parentheses
-   csharp_space_between_method_declaration_parameter_list_parentheses
-   csharp_space_between_parentheses
-   csharp_style_expression_bodied_accessors
-   csharp_style_expression_bodied_constructors
-   csharp_style_expression_bodied_indexers
-   csharp_style_expression_bodied_methods
-   csharp_style_expression_bodied_operators
-   csharp_style_expression_bodied_properties
-   csharp_style_inlined_variable_declaration
-   csharp_style_pattern_local_over_anonymous_function
-   csharp_style_pattern_matching_over_as_with_null_check
-   csharp_style_var_for_built_in_types
-   csharp_style_var_when_type_is_apparent
-   dotnet_sort_system_directives_first
-   dotnet_style_explicit_tuple_names
-   dotnet_style_object_initializer
-   dotnet_style_predefined_type_for_locals_parameters_members
-   dotnet_style_predefined_type_for_member_access
-   dotnet_style_prefer_inferred_anonymous_type_member_names
-   dotnet_style_qualification_for_event
-   dotnet_style_qualification_for_field
-   dotnet_style_qualification_for_method
-   dotnet_style_qualification_for_property
-   dotnet_style_require_accessibility_modifiers

## 问： Visual Studio IntelliCode 扩展提供其他功能吗？

我们正在努力开发诸多功能，非常高兴在其可用时与大家分享。 可通过 [https://aka.ms/intellicode](https://aka.ms/intellicode) 注册来了解新闻和更新，第一时间获得可用新功能的通知。

## 问：与常规 IntelliSense 比较，由 IntelliCode 提供支持的“AI 辅助 IntelliSense”有什么优势？

借助 IntelliCode，完成列表可建议供开发人员使用的最可能正确的 API，而不是呈现简单的按字母顺序排列的成员列表。 它使用开发人员当前的代码上下文以及基于 GitHub 上 2000 个高质量开放源代码的模式（每个具有超过 100 个星标），提供此动态列表。 结果形成一种预测最可能、最相关的 API 调用的模型。

## 问：IntelliCode 完成建议有多大用处？

我们在 Microsoft 内部使用 IntelliCode 的建议已有一段时间，我们相信这些建议很有用。 但从根本上讲，这取决于这些建议在你编码时有多大用处。 我们希望你能够尝试使用 Visual Studio [ IntelliCode 扩展](https://go.microsoft.com/fwlink/?linkid=872707)。 请告知我们它如何对你有用，并向我们发送你的反馈。 我们还将根据你所采取的建议来训练我们的模型，并随着模型的改进更新扩展。

> [!NOTE]
> 不会收集任何用户定义的代码。 请参阅关于[隐私](#privacy)的问题。

## 问： IntelliCode 的未来是什么样的？

我们正在探索各种方法，使用 AI 和其他先进技术提高开发人员工作效率。 在 Microsoft Build 2018 中，我们展示了一些我们认为 AI 可辅助开发人员的方案的早期观点，以及更多内容！ 我们希望试用我们所展示功能的开发人员提供反馈，请通过 [https://aka.ms/intellicode](https://aka.ms/intellicode) 注册，了解新闻和更新。

## 问： 定价是多少？

目前还没有关于定价的公告。

## 问： 什么时候发布 IntelliCode？

IntelliCode 的 AI 辅助 IntelliSense 当前处于第一个试验预览版。 我们将继续更新试验扩展，并将在未来增加更多功能。 我们目前没有最终发布的计划，但是希望开发人员提供反馈，以便我们提供最佳体验。 请注册，通过 [https://aka.ms/intellicode](https://aka.ms/intellicode) 获取新闻和更新。

## 问： 这种体验仅在 Visual Studio 中提供且仅对 C# 适用吗？

C# 代码库上 Visual Studio 2017 中的 Build 2018 展示了这种体验。 但是，我们希望未来将 IntelliCode 扩展到 Visual Studio 系列中的更多语言和工具。

## 问： <a name="whynointellisense"/> 在 C# 编辑体验中，我无法看到 IntelliCode 建议 - 什么情况？

IntelliCode 建议出现在 C# 的标准 Visual Studio IntelliSense UI 中。 重写该 UI 的扩展可防止 IntelliCode“加星标”建议出现在列表顶部。 你可以通过关闭扩展然后再次尝试 IntelliSense 来验证是否由于扩展导致此行为。

如果这样无法解决问题，请通过 Visual Studio [报告问题](https://docs.microsoft.com/en-us/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)功能报告问题，并在报告中提及 IntelliCode。

## 问： 需要哪个版本的 Visual Studio 来运行此扩展？

Visual Studio 2017 版本 15.7 预览版 5 及更高版本（所有 SKU）支持 Visual Studio IntelliCode 扩展。 如果没有安装要求的最低版本，会显示“此扩展不能安装在任何当前安装的产品上”， 扩展安装将中止。

## 问： 此体验仅提供英文版吗？

IntelliCode 目前是一个预览扩展，我们迫切希望了解这些功能对广大客户有多大用处。 当我们取消 IntelliCode 预览时，肯定会根据反馈考虑首先支持哪个区域或语言，以及如何将其打包。

## <a name="privacy"/>问：隐私方面呢？ 是否会将我的代码发送到云？ 哪些客户数据将发送到 Microsoft？

开发人员今天受邀体验了 Visual Studio IntelliCode（作为试验预览版扩展）。 此扩展的目的是使开发人员测试 IntelliCode 的功能并向产品团队提供反馈。

我们从扩展中捕获一些匿名使用情况和错误报告数据，以帮助改进产品。 不会向 Microsoft 发送用户定义代码，但是我们会收集关于使用 IntelliCode 结果的信息。 数据只包含从 IntelliCode 的建议列表中选择的开放源代码和 .NET 类型以及成员。 开发人员可以选择退出 [Visual Studio 体验改善计划](../../ide/visual-studio-experience-improvement-program.md)，这样也会关闭 IntelliCode 扩展的数据收集。 从菜单栏选择“帮助” > “发送反馈” > “设置”。 在“Visual Studio 体验改善计划”对话框中，选择“不，我不想参加”，然后选择“确定” 。

IntelliCode 扩展可能会定期要求开发人员完成一项匿名调查。 用户可以注册以获取新闻和将来的个人预览版，但目前使用试验扩展不要求进行该操作。

未来的功能可能需要服务的访问权限，这要求注册。 这些功能可用于个人预览版时，我们将发布更多详细信息。
