---
title: Visual Studio Feedback Client 2017 工作负载和组件 ID
description: 使用 Visual Studio 工作负载和组件 ID 提供有关 Visual Studio Team Services 或 Team Foundation Server 的大量反馈
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 05/07/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.assetid: 7392a100-100c-458c-9394-828695109015
ms.workload:
- multiple
ms.openlocfilehash: 56b58ec44ecae6e1e0bbd6c0d3e4bc000c1bcf28
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282997"
---
# <a name="visual-studio-feedback-client-2017-component-directory"></a>Visual Studio Feedback Client 2017 组件目录

本页的表中列出了可用于通过使用命令行安装 Visual Studio 或可指定为 VSIX 清单中的依赖项的 ID。 请注意，我们将在发布 Visual Studio 更新时添加其他组件。

另请注意以下有关本页的注意事项：

* 每个工作负载均有其自己的部分，后跟工作负载 ID 和适用于工作负载的组件表格。
* 默认情况下，安装工作负载时将安装**必需**组件。
* 如果愿意，还可以安装**推荐**和**可选**组件。
* 我们还添加了一个部分，此部分列出了不属于任何工作负载的其他组件。

在 VSIX 清单中设置依赖项时，必须仅指定组件 ID。 使用本页中的表格来确定最小组件依赖项。 在某些情况下，这可能意味着仅从工作负载指定一个组件。 在其他情况下，这可能意味着你从单个工作负载指定多个组件或从多个工作负载指定多个组件。 有关详细信息，请参阅[如何：将扩展性项目迁移到 Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) 页。

有关如何使用这些 ID 的详细信息，请参阅[使用命令行参数安装 Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) 页。 另外，有关其他产品的工作负载和组件 ID 的列表，请参阅 [Visual Studio 2017 工作负载和组件 ID](workload-and-component-ids.md) 页。

## <a name="feedback-client"></a>Feedback Client

**ID:** Microsoft.VisualStudio.Workload.FeedbackClient

**说明：** 利益干系人可以使用 Feedback 客户端提供有关 Visual Studio Team Services 或者 Team Foundation Server 的大量反馈。

### <a name="components-included-by-this-workload"></a>此工作负载所包含的组件

组件 ID | name | 版本 | 依赖项类型
--- | --- | --- | ---
Microsoft.VisualStudio.Component.TestTools.FeedbackClient | Microsoft Feedback Client | 15.6.27406.0 | 必需

## <a name="unaffiliated-components"></a>独立组件

这些组件不随附于任何工作负载，但可选择作为单个组件。

组件 ID | name | 版本
--- | --- | ---
n/a | 不可用 | n/a

## <a name="get-support"></a>获取支持

有时也会遇到问题。 如果 Visual Studio 安装失败，请参阅 [Visual Studio 2017 安装和升级问题疑难解答](troubleshooting-installation-issues.md)页。 如果所有的疑难解答步骤都没有帮助，请通过实时聊天与我们联系，以获得安装帮助（仅限英语）。 有关详细信息，请参阅 [Visual Studio 支持页](https://visualstudio.microsoft.com/vs/support/#talktous)。

下面是另外几个支持选项：

* 可以通过[报告问题](../ide/how-to-report-a-problem-with-visual-studio-2017.md)工具（会出现在 Visual Studio 安装程序和 Visual Studio IDE 中）向我们报告产品问题。
* 可以在 [UserVoice](https://visualstudio.uservoice.com/forums/121579) 上与我们分享产品建议。
* 可以在 [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)中跟踪产品问题并找到答案。
* 此外，还可以通过 [Gitter 社区的 Visual Studio 对话](https://gitter.im/Microsoft/VisualStudio)与我们和其他 Visual Studio 开发人员进行交流。 （此选项需要 [GitHub](https://github.com/) 帐户。）

## <a name="see-also"></a>请参阅

* [Visual Studio 工作负荷和组件 ID](workload-and-component-ids.md)
* [Visual Studio 管理员指南](visual-studio-administrator-guide.md)
* [使用命令行参数安装 Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
  * [命令行参数示例](command-line-parameter-examples.md)
* [创建 Visual Studio 的脱机安装](create-an-offline-installation-of-visual-studio.md)
