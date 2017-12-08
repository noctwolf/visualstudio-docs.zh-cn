---
title: "管理员职责 | Visual Studio Marketplace"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: "了解订阅管理员的职责。"
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 0ac48059a0491b9009b6ff87fd6e05075565c028
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="administrator-overview"></a>管理员概述
## <a name="roles--responsibilities"></a>角色和职责
作为对 Microsoft 产品和服务折扣价的回报，你的组织同意接受有关 Visual Studio 订阅的某些职责和限制。 Visual Studio 管理员有四大职责：
1.  **了解 Visual Studio 订阅的权益和限制。** 通过正确了解你的权益，既可降低使用云服务带来的硬件成本，又可降低预生产环境每用户许可证产生的软件成本。 
2.  **将 Visual Studio 订阅分配给特定的指定人员并鼓励其使用。** 合同中要求将 Visual Studio 订阅分配给特定的指定人员。 跟进这些已分配人员，确保他们获取并充分利用其 Visual Studio 订阅包含的权益。
3.  **准确清点预生产环境。** 清点操作至关重要，它能确保与 Visual Studio 授权软件交互的所有用户都获得自己的 Visual Studio 订阅的适当授权。 
4.  **跟踪用户分配变更，按计划获取附加许可证。** Microsoft 批量许可协议允许你灵活使用和分配 Visual Studio 订阅。 相应地，你需要跟踪软件使用情况和用户分配的变更，并按协议规定的计划处理附加许可证订单。

## <a name="benefits-and-limitations"></a>权益和限制
利用 Visual Studio 订阅，开发团队成员可以安装并使用软件来设计、开发、测试、评估和演示其他软件。 Visual Studio 订阅软件不能用于生产环境。 

|                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 基于用户的授权                     | MSDN 平台和所有级别的 Visual Studio 订阅均按用户授权。 与这些产品和服务随附的软件进行交互（安装、配置或访问）的每个开发团队成员都需要有自己的 Visual Studio 订阅。                                                                                                                                                                                                                                                                                                                                  |
| 无限制的安装                  | 每个授权用户均可在任意数目的设备上安装并使用软件来设计、开发、测试、评估和演示软件。 Microsoft Office 是其中的特例，该产品只能用于一个桌面。 Visual Studio 授权软件可以在工作单位、家里、学校以及客户办公室设备或第三方托管的专用硬件上安装和使用。                                                                                                                                                                                                                                  |
| 不能用于生产环境 | Visual Studio 订阅软件不能用于生产环境，包括最终用户因验收测试或反馈以外的目的访问的所有环境，连接到生产数据库的环境，支持灾难恢复或生产备份的环境，或用于在活动高峰期间进行生产的环境。 特例包括 [Visual Studio 授权白皮书](http://aka.ms/vslicensing)中规定的某些订阅级别的特定权益。                                                                                            |
| 许可证重新分配                     | 用户离开团队且不再需要许可证时，你可以在 90 天后重新分配该许可证。 重新分配许可证时不会替换已在使用的任何产品密钥。 此功能与批量许可服务中心 (VLSC) 已有的功能不同。 已使用的所有权益（如 Pluralsight）都将清零。                                                                                                                                                                                                                                                 |
| 最终用户特例                  | 在软件开发项目末期，最终用户通常会检查应用程序，确定其是否符合必要的发布条件。 此过程称为用户验收测试 (UAT)。 业务发起人或产品经理等团队成员可以充当最终用户代理。 没有 Visual Studio 订阅的最终用户如果以其他符合所有 Visual Studio 许可条款的方式使用软件，则可访问软件进行 UAT。 仅在极少数情况下，一些主要职责是设计、开发或测试软件的人员也有资格充当“最终用户”。 |

## <a name="inventory-of-pre-production-environment"></a>清点预生产环境
Visual Studio 订阅对用户而非设备计数，从而简化了资产管理。

Visual Studio 管理员必须将 Visual Studio 订阅分配给**特定的指定人员**。 **不允许**采用诸如 Dev1、Dev2 或 Dev3 之类的命名约定。

下面是一些简化预生产环境清点过程的方法：
- 检查用户分配。 Microsoft 提供名为 [Visual Studio 管理门户](https://manage.visualstudio.com/)的网站，帮助你跟踪 Visual Studio 订阅分配。
- 使用本地或基于云的 Active Directory 列出用户。 如果使用 Active Directory 管理用户访问权限，可能能够根据目录成员身份识别开发用户和测试用户。
- 使用自动化工具清点系统。 可能还需要使用软件清点工具，帮助管理软件资产以及区分预生产环境与生产环境。 许多拥有 Microsoft System Center 的客户会创建命名约定，帮助在清点过程中自动处理这部分内容。
- 以手动核对的方式获得帮助。 让员工参与进来，帮助核对开发和测试用户与开发和测试环境。 

## <a name="large-teams-and-internal-contractors"></a>大型团队和内部承包商
Visual Studio 订阅管理员负责确保与 Visual Studio 授权软件交互的每个用户都获得自己的 Visual Studio 订阅的适当授权。
### <a name="internal-teams"></a>内部团队
现代软件组织通常包括来自多个群体的利益干系人。 确定每个群体的联系人，这些联系人可帮助你跟踪用户清单和变更。 每个组织各有不同，但参与开发的典型团队名单可能包括：
- 软件工程团队。 
- 业务团队，包括产品所有者和业务分析人员。
- 项目管理团队。 
- 质量团队，包括 QA 人员和手动测试人员。
- IT 运维团队，包括预生产和实验室基础设施经理。

### <a name="external-contractors-and-partners"></a>外部承包商和合作伙伴
外部承包商可以引入许可证以使用你的 Visual Studio 授权环境。 Microsoft 认证合作伙伴可获取一些免费 Visual Studio 订阅供内部使用。 但是，这些订阅不能用于产生收入的活动，比如为客户开发自定义软件。 请合作伙伴向你发送一封确认函，说明他们正在提供的许可证以及需要你购买的许可证。

## <a name="track-user-assignment-and-process-orders"></a>跟踪用户分配和处理订单
Visual Studio 订阅管理员需要跟踪 Visual Studio 使用情况，并按批量许可协议或 Microsoft 产品和服务协议规定的计划处理因使用量增加而产生的订单。 新的 Visual Studio 订阅管理门户提供一个有用的跟踪器，可显示可用和已用的许可证，从而简化了这一过程。
### <a name="high-water-mark-of-usage"></a>使用量高水位线
**在以下情况下，贵公司购买 Visual Studio 订阅的义务立即生效：**
- 向用户分配许可证。
- 用户与 Visual Studio 软件交互。

你的完全购买义务由**使用量高水位线**决定。 此水位线是指日常用户分配最大数量或与 Visual Studio 软件交互的用户最大数量（以两者中的较高者为准）。
1.  Visual Studio 订阅管理员可通过将 Visual Studio 订阅分配给个人，提高使用量高水位线。
2.  Visual Studio 订阅管理员可以自初始分配之日起的 90 天后，将一个订阅者的订阅重新分配给另一个订阅者。 为避免人为造成高水位线，在执行此操作时应始终先删除现有订阅，然后再添加新订阅。
3.  Visual Studio 订阅管理员可以更改分配给个人的订阅级别，这会形成一个分配级别的降低，另一个分配级别的提高。 降低分配给某个订阅者的订阅级别后，该订阅者必须立即停止使用并卸载任何只存在于较高级别订阅中的内容。 

### <a name="open-license-and-open-value"></a>开放式许可证和开放式价值
你可能正在通过另一个 Microsoft 批量许可计划（如 Microsoft 开放式许可证或开放式价值）分配订阅。 如果是这样，则必须在用户（员工或外部承包商）开始与 Visual Studio 授权软件交互的当月处理附加用户订单。
### <a name="enterprise-agreements"></a>企业协议
Microsoft 企业协议 (EA)、MPSA 和 Select Plus 协议允许你随时间推移灵活地使用和授权 Visual Studio 软件。 Visual Studio 管理员必须制定年度校准订单，使软件许可证数量在协议期间达到规定的使用量高水位线。