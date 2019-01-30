---
title: 对应用程序进行全球化和本地化
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- globalization [Visual Studio]
- Visual Basic code, international applications
- C#, international applications
- localization [Visual Studio]
- world-ready applications
- international applications [Visual Studio]
ms.assetid: 4d9815ae-3e80-4b4d-933d-f8309aee18d5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 850a10ca569afa9b5202059b12998570813e789b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54961226"
---
# <a name="globalizing-and-localizing-applications"></a>对应用程序进行全球化和本地化

如果计划向国际用户分发应用程序，则在设计和开发阶段需要牢记几个事项。 即使现在没有此类计划，如果你的计划在以后版本的应用程序中出现变动，一些预先工作也会大大简化所需操作。 利用 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 中内置的服务，可以轻松使用 Visual Studio 的托管开发来开发适应不同区域设置的单个应用程序。

## <a name="resources"></a>资源

 从设计之初开始，Visual Studio 的设计目的就是通过利用 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 中内置的服务来简化面向国际用户的开发工作。 以下文章将介绍 Visual Studio 中内置的国际化功能。

 [基于 .NET Framework 的国际应用程序简介](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)：介绍有关使用 Visual Studio 和 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 面向国际市场开发软件的概念。

 [本地化应用程序](../ide/localizing-applications.md)：提供针对给定区域性自定义应用程序的页面链接。

 [全球化应用程序](../ide/globalizing-applications.md)：提供有关创建支持多种区域性的应用程序的页面链接。

## <a name="see-also"></a>请参阅

- [开发全球通用应用程序的最佳做法](/dotnet/standard/globalization-localization/best-practices-for-developing-world-ready-apps)为国际受众提供关于编程的背景信息。
- [类库概述](/dotnet/standard/class-library-overview)介绍可加快和优化开发过程并提供对系统功能的访问的类、接口和值类型。
- <xref:System.Globalization> 指出该命名空间中的类，这些类定义区域性相关信息，包括语言、国家/地区、使用的日历、日期格式形式、货币、数字以及字符串排序顺序。
- <xref:System.Resources> 指出该命名空间中的类和接口，这些类和接口使开发人员能够创建、存储和管理应用程序中所使用的、各种区域性特定的各种资源。