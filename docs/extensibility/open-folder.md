---
title: Visual Studio 打开文件夹扩展性概述 |Microsoft 文档
ms.custom: ''
ms.date: 02/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94c3f8bf-1de3-40ea-aded-7f40c4b314c7
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 1bbe9638777bc672a0cec494498a38f4bd8ce1f4
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="open-folder-extensibility"></a>打开文件夹扩展性

[打开文件夹](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)功能允许用户打开任何基本代码在 Visual Studio 中无需项目或解决方案文件。 打开文件夹提供的功能用户应该从 Visual Studio 如：

* 解决方案资源管理器集成和搜索
* 编辑器着色
* 转到导航
* 在文件搜索中查找

时与工作负荷如.NET 和 c + + 开发一起使用，用户也可以获得：

* 丰富智能感知
* 特定于语言的功能

使用打开的文件夹，扩展插件作者可以创建任何语言的丰富功能。 没有要支持构建、 调试和符号搜索中用户的任何文件的基本代码的 Api。 当前的扩展程序可以更新其现有的 Visual Studio 功能，以了解没有的项目或解决方案支持的代码。

## <a name="an-api-without-project-systems"></a>API 以不项目系统

从历史上看，Visual Studio 仅理解解决方案和项目使用项目系统中的文件。 项目系统负责加载的项目的功能和用户交互。 它了解哪些文件其项目包含的可视表示形式的项目内容，对其他项目依赖项，并且基础修改项目文件。 它是通过这些层次结构和其他组件完成的工作，代表用户的功能。 并非所有基本代码很好地表示项目和解决方案结构中。 脚本语言和 c + + 编写适用于 Linux 的开放源代码代码是很好的示例。 与打开的文件夹，Visual Studio 提供了让用户使用其源代码进行交互的新方法。

打开文件夹 Api 正在`Microsoft.VisualStudio.Workspace.*`命名空间和可用于扩展程序来生成和使用数据或解决打开文件夹中的文件的操作。 扩展可以使用这些 Api 来提供多个区域，包括的功能：

- [工作区](workspaces.md)-从开始点的打开文件夹扩展性是工作区和及其 Api。
- [文件上下文和操作](workspace-file-contexts.md)-文件通过文件上下文提供的特定代码智能。
- [索引](workspace-indexing.md)-收集并保留有关打开文件夹工作区的数据。
- [语言服务](workspace-language-services.md)-将语言服务集成到工作区打开的文件夹。
- [生成](workspace-build.md)-生成针对打开文件夹工作区的支持。

使用以下类型的功能将需要采用新的 Api 以支持打开文件夹：

- `IVsHierarchy`
- `IVsProject`
- `DTE`

## <a name="feedback-comments-issues"></a>反馈，注释问题

打开文件夹和`Microsoft.VisualStudio.Workspace.*`Api 是进行活动开发。 如果你看到意外的行为，请参阅感兴趣的版本的已知的问题。 开发人员社区是投票并创建任何问题的建议的位置。 对于每个反馈，我们强烈建议你的问题的详细的说明。 包括你正在开发的 Visual Studio 版本、 （你已实现和你在与所进行的交互） 正在使用的 Api、 预期的结果和实际的结果。 如果可能，包括 devenv.exe 进程的转储。 使用跟踪上提供反馈的 GitHub 的问题和相关文档。

## <a name="next-steps"></a>后续步骤

* [工作区](workspaces.md)-了解有关 API 的打开文件夹工作区。