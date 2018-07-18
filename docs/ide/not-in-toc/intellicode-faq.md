---
title: IntelliCode 问题和解答
ms.date: 05/22/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
ms.openlocfilehash: f0410b3ffd04c42f316d99c150253e72bb1b1944
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34468799"
---
# Visual Studio IntelliCode 常见问题解答

感谢关注 Visual Studio IntelliCode！ 我们提供了此简短的常见问题解答，希望能够回答你的一些问题。

## 问： 什么是 Visual Studio IntelliCode？

在 Build 2018 中，我们宣布推出 Visual Studio IntelliCode，这是一种使用 AI 增强软件开发的新功能。 IntelliCode 有助于开发人员和团队自信地进行编码、更快地发现问题并专注于代码评审。

我们展示了 IntelliCode 如何通过以下方式增强软件开发过程的早期观点：

- 提供上下文感知代码完成
- 指导开发人员遵守团队的模式和样式
- 发现难以察觉的代码问题
- 将关注点集中到重要领域，从而专注代码评审

开发人员可在 [https://aka.ms/intellicode](https://aka.ms/intellicode) 上找到详细信息并注册，以获取新闻和将来的个人预览版。

## 问： Visual Studio IntelliCode 为客户提供哪些功能？

Visual Studio IntelliCode 是通过人工智能 (AI) 提供新的工作效率增强功能的一系列功能。

开发人员可以为 Visual Studio 2017 版本 15.7 及更高版本[下载试验扩展](https://go.microsoft.com/fwlink/?linkid=872707)。 该扩展提供增强的 IntelliSense，可预测供开发人员使用的最可能正确的 API，而不仅仅是呈现按字母顺序排列的成员列表。 它使用开发人员当前的代码上下文和模式来提供此动态列表。 我们将在未来几个月中更新具有更多功能的扩展。

## 问： Visual Studio IntelliCode 扩展提供其他功能吗？ 例如 editconfig 生成？

我们正在努力开发诸多功能，非常高兴在其可用时与大家分享。 我们在 Microsoft Build 2018 介绍了早期的内部版本工具，它为采用 C# 的代码样式和格式推断 editorconfig 设置。 该工具尚未进入试验扩展阶段，不过计划在不久后推出。 可通过 [https://aka.ms/intellicode](https://aka.ms/intellicode) 注册来了解新闻和更新，第一时间获得可用新功能的通知。

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

IntelliCode 建议出现在 C# 的标准 Visual Studio IntelliSense 体验中。 重写该体验的扩展可防止 IntelliCode“加星标”建议出现在列表顶部。 你可以通过关闭扩展然后再次尝试 IntelliSense 来验证是否由于扩展导致此行为。

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
