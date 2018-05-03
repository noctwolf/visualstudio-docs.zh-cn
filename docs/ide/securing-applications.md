---
title: 在 Visual Studio 中保护应用程序
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- security [Visual Studio], applications
- application design, securability
ms.assetid: 7d32c4cf-8bec-4307-a2a8-42f0ceddf3eb
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ec93a207f30218492bbbb3161f073ecfdca975cf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="secure-applications"></a>保护应用程序

虽然大部分应用程序会面临共同的安全挑战，不过每个应用程序域都具有自己的安全挑战。

## <a name="general-security-considerations"></a>一般安全注意事项
 每种语言都有其自己的安全注意事项和挑战。

 [安全性最佳做法](/cpp/top/security-best-practices-for-cpp)提供有关在 Visual C++ 中工作时可用的安全功能和做法的信息。

 [安全性和编程（C# 和 Visual Basic）](https://msdn.microsoft.com/library/ms233782(v=vs.100).aspx)提供有关 Visual Basic 和 C# 开发人员面临的前三大安全问题的信息：权限、Web 应用和 Visual Studio 安装。

## <a name="secure-mobile-applications"></a>保护移动应用程序
 随着移动设备普及程度的增加，这些设备上的信息和数据的安全性便变得更加重要。

 [设备的安全注意事项](http://msdn.microsoft.com/45fab484-8718-452e-8210-04fda3c6cb87)介绍影响设备安全策略的几个因素。

 [.NET Compact Framework 的安全性目标](http://msdn.microsoft.com/64ac2770-e2bc-40a3-abbf-56c8a2c0e364)介绍 .NET Compact Framework 安全性的目标。

 [设计安全的移动 Web 窗体页](http://msdn.microsoft.com/b69727c1-f81f-4221-a116-8f92f769365f)讨论规划、实现和支持无线网络和移动设备中的安全性。

## <a name="secure-web-applications"></a>保护 Web 应用的安全
 编写糟糕的网页可能会危害整个服务器以及（可能）整个网络的完整性和安全性。 因此，你必须在规划 Web 应用时检查安全注意事项。

 [ASP.NET 安全体系结构](http://msdn.microsoft.com/Library/c34d6f4f-f64d-4697-bd32-02dd2ddf726f)提供与安全性相关的 ASP.NET 基础结构和子系统关系的概述。

 [ASP.NET Web 应用程序安全性](http://msdn.microsoft.com/Library/658d0430-1644-4744-b52d-08b0d6fcacb8)详细介绍如何解决 ASP.NET 中的授权和身份验证问题。

 [如何：使用传输安全性](http://msdn.microsoft.com/16210e41-5492-4cc8-9002-7366b1fc7297)介绍如何在连接到 WCF 服务时使用传输安全性进行身份验证。

## <a name="secure-desktop-applications"></a>保护桌面应用程序的安全
 桌面应用程序的安全性设计是应用程序开发中一个必不可少的步骤。

 [Windows 窗体安全](/dotnet/framework/winforms/windows-forms-security)提供 Windows 窗体安全实现的概述。

## <a name="see-also"></a>请参阅

- [安全性](../ide/security-in-visual-studio.md)