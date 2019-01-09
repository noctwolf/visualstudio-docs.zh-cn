---
title: 升级 Dotfuscator Community Edition (CE)
ms.date: 02/08/2017
ms.devlang: dotnet
ms.prod: visual-studio-dev15
ms.topic: conceptual
keywords: Dotfuscator, Dotfuscator CE, PreEmptive, PreEmptive Solutions, PreEmptive Protection, 保护, 社区版, 混淆, .NET, 免费, Visual Studio 2017, 升级, 命令行
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
- Dotfuscator upgrade
- upgrade Dotfuscator
- upgrading Dotfuscator
- register Dotfuscator
- registering Dotfuscator
- Dotfuscator command line
- Dotfuscator Professional
description: 了解如何升级 Visual Studio 2017 中包含的免费 Dotfuscator Community Edition。
ms.assetid: c7c60904-27f9-4f1f-b79b-ddf65041b810
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: douge
ms.openlocfilehash: e7c4c6069c68708d869d58dfe60aa226983afcf2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53871867"
---
# <a name="upgrade-dotfuscator-community-edition-ce"></a>升级 Dotfuscator Community Edition (CE)

Dotfuscator Community Edition (Dotfuscator CE) 直接向使用 Microsoft Visual Studio 的所有开发人员提供许多应用程序保护和强化功能。
升级 Dotfuscator 版本的用户还可使用更多功能。

## <a name="registering-dotfuscator-ce"></a>注册 Dotfuscator CE

Dotfuscator CE 的注册用户可以访问其他功能（如[命令行支持][cli]），将 Dotfuscator CE 轻松集成到自动生成过程中。 注册后也可访问 Lucidator，它是用于[解码混淆堆栈跟踪][decode-obfuscated]的一款内置工具。

注册快速、简单而且免费。
若要注册 Dotfuscator CE，请参阅[完整 Dotfuscator CE 用户指南“入门”页上的“注册 Dotfuscator CE”部分][register-ce]。

## <a name="dotfuscator-professional"></a>Dotfuscator Professional

虽然 Dotfuscator Community Edition 提供了基本级别的保护，但 **_PreEmptive Protection - Dotfuscator_ Professional Edition** 包含增强的模糊处理转换和保护功能。 增强的转换和功能包括：

* 知识产权保护
  * 其他重命名选项，包括 Enhanced Overload Induction™ 和随机标识符选择。
  * 用于解码经过模糊处理的堆栈跟踪的工具。
  * 访问企业级模糊处理转换，包括[以破坏自动化代码反编译为目标的转换][control-flow]。
  * 能够[隐匿敏感字符串][string-encryption]因此不可能对反编译代码进行简单搜索。
  * 能够[将所有权和分发字符串审慎嵌入程序集][watermarking]，因此可以确定未经授权的软件泄漏的根源。
  * 能够[将多个程序集组合成一个][linking]，不再分离关注点，让攻击者更加难以确定代码元素的角色。
  * 能够[自动删除应用程序中未使用的代码][pruning]，减少附带的敏感代码量。
* 应用程序完整性保护
  * 其他[应用程序防御行为][check-actions]。
  * 能够在应用程序生命周期截止前提供警告期。
  * 能够在生命周期警告期内或在截止时间后通知应用程序代码。

Dotfuscator Professional 是行业标准的 [.NET 模糊处理程序][net-obfuscator]，适用于需要持续支持、维护和产品更新的企业开发人员。
此外，Dotfuscator Professional 提供与 Visual Studio 的更紧密集成，并获得商业使用许可。

有关 Dotfuscator Professional 的高级应用程序保护功能的详细信息，请访问 PreEmptive Solutions 的 [Dotfuscator 概述页][product-about]和[将其与 Community Edition 进行比较][product-compare]。
[可通过 preemptive.com 获取全面支持的试用版][eval]。

## <a name="see-also"></a>请参阅

[完整 Dotfuscator CE 用户指南中的本主题][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[control-flow]:  https://www.preemptive.com/products/dotfuscator/features#controlflow
[string-encryption]:  https://www.preemptive.com/products/dotfuscator/features#string
[watermarking]:  https://www.preemptive.com/products/dotfuscator/features#watermarking
[linking]:  https://www.preemptive.com/products/dotfuscator/features#linking
[pruning]:  https://www.preemptive.com/products/dotfuscator/features#pruning

[check-actions]:  https://www.preemptive.com/dotfuscator/pro/userguide/en/protection_checks_overview.html#actions

[net-obfuscator]:  https://www.preemptive.com/products/dotfuscator/overview
[eval]:  https://www.preemptive.com/eval-request

[product-about]:  https://www.preemptive.com/products/dotfuscator/overview
[product-compare]:  https://www.preemptive.com/products/dotfuscator/compare-editions

[cli]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_cli.html
[register-ce]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html#register

[full]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_upgrades.html
[decode-obfuscated]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_decode_stack_trace.html