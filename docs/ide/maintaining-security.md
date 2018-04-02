---
title: 维护 Visual Studio 中的应用程序安全性 | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: article
helpviewer_keywords:
- unauthorized access
- Baseline Security Analyzer
- Microsoft Baseline Security Analyzer
- security [.NET Framework], best practices
- MBSA (Microsoft Baseline Security Analyzer)
- security [.NET Framework], maintaining after deployment
ms.assetid: 621d10c1-842b-4902-be60-bb9719591751
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f0594f7c9af507f2c68ac4f0cc80b1d2e38d2a51
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="maintaining-security"></a>维护安全性

常言道安全靠常抓不懈。 尽管你在应用程序的设计和开发过程中非常专注于安全性，还是应当假设在部署之后会出现安全漏洞。 通过严格检查应用程序和分析事件日志，你可能会发现一些以前隐蔽起来的漏洞。

此外，你不仅必须对自己的应用程序保持警惕，还必须随时了解运行应用程序的平台以及应用程序所依赖的其他产品的安全威胁和漏洞。

[安全、隐私和帐户](https://support.microsoft.com/products/microsoft-account?category=privacy#security-privacy-accounts-help=windows-8&v0h=winrttab1&v1h=win8tab1&v2h=win7tab1&v3h=winvistatab1)&mdash;获取安全、隐私与用户帐户方面的帮助，包括有关病毒、密码、家长控制、防火墙和驱动器加密的信息。

[Microsoft 安全更新公告](https://technet.microsoft.com/security/bulletins.aspx)&mdash;使用该页可以很容易找到以前发布的公告。 安全公告旨在为 IT 专业人员提供有关安全更新的详细信息。

[Microsoft 基准安全分析器](https://www.microsoft.com/download/details.aspx?id=7558)&mdash;Microsoft 基准安全分析器 (MBSA) 是一个供个人家庭用户、企业用户或管理员使用的工具，它能够在一个或多个基于 Windows 的计算机上扫描常见的安全配置错误。