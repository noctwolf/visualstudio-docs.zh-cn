---
title: 客户体验改善计划
description: 了解如何在 Visual Studio 中管理隐私设置。
ms.date: 05/21/2018
ms.topic: conceptual
author: PoulChapman
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f64655dd1afca25ca0c216fa93cb9f85fb4a5b41
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2019
ms.locfileid: "57323113"
---
# <a name="visual-studio-customer-experience-improvement-program"></a>Visual Studio 客户体验改善计划

Visual Studio 客户体验改善计划 (VSCEIP) 旨在随着时间推移帮助 Microsoft 改进 Visual Studio。 此程序[收集有关错误的信息](../ide/diagnostic-data-collection.md)、计算机硬件以及 Visual Studio 的使用方式，而不中断用户在计算机中的任务。 收集的信息帮助 Microsoft 确定要改善的功能。 本文档介绍如何选择加入或退出 VSCEIP。

[!INCLUDE [gdpr-hybrid-note](../misc/includes/gdpr-hybrid-note.md)]

## <a name="opt-in-or-out"></a>选择加入或退出

VSCEIP 默认开启。 可以按照以下步骤将其关闭或者再次打开：

1. 启动 Visual Studio。

1. 从“帮助”菜单，指向“发送反馈”，然后选择“设置”。

   “Visual Studio 体验改善计划”对话框随即打开。

1. 若要选择退出，请选择“否，我不想参加”，然后选择“确定”。 若要选择加入，请选择“是，我愿意参加”，然后选择“确定”。

   ![“Visual Studio 体验改善计划”对话框](media/experience-improvement-program.png)

### <a name="registry-settings"></a>注册表设置

如果安装 [Visual Studio 生成工具](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2017)，必须更新注册表来配置 VSCEIP。 企业客户可以设置基于注册表的策略，利用这种方式构造选择加入或不加入 VSCEIP 的组策略。

相关注册表项和设置如下所示：

::: moniker range="vs-2017"

- 在 64 位操作系统上，Key = HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSCommon\15.0\SQM
- 在 32 位操作系统上，Key = HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSCommon\15.0\SQM
- 启用“组策略”时，Key = HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\VisualStudio\SQM

::: moniker-end

::: moniker range=">=vs-2019"

- 在 64 位操作系统上，Key = HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSCommon\16.0\SQM
- 在 32 位操作系统上，Key = HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSCommon\16.0\SQM
- 启用“组策略”时，Key = HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\VisualStudio\SQM

::: moniker-end

Entry = OptIn

Value = (DWORD)

- “0”为选择退出（关闭 VSCEIP）
- “1”为选择加入（开启 VSCEIP）

> [!CAUTION]
> 错误地编辑注册表可能会严重损坏您的系统。 在对注册表进行更改之前，应备份计算机上任何有价值的数据。 如果在应用手动更改之后遇到问题，也可以使用“最近一次的正确配置”启动选项。

有关 VSCEIP 收集、处理或传输的信息的详情，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。

## <a name="see-also"></a>请参阅

* [Visual Studio 收集的诊断信息](diagnostic-data-collection.md)
* [与我们交流](../ide/talk-to-us.md)
* [如何报告 Visual Studio 的问题](../ide/how-to-report-a-problem-with-visual-studio.md)
* [Visual Studio 开发者社区](https://developercommunity.visualstudio.com/)
* [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)
