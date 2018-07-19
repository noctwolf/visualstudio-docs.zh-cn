---
title: 调试和托管进程 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], hosting process
- hosting process
ms.assetid: d0f0b9a6-2a6e-463d-b6ea-9518ee727933
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 74f584eb9217e46215405aa0786e5fa10e6034a9
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2018
ms.locfileid: "37088896"
---
# <a name="debugging-and-the-hosting-process"></a>调试和承载进程
Visual Studio 宿主进程提高了调试器性能，并启用了新的调试器功能，如部分信任调试和设计时表达式计算。 如果需要，你可以禁用宿主进程。 以下部分描述用宿主进程和不用宿主进程进行调试的一些差异。

## <a name="partial-trust-debugging-and-click-once-security"></a>部分信任调试和 Click-Once 安全
 部分信任调试需要宿主进程。 如果禁用宿主进程，部分信任调试将不工作，即使在 **“项目属性”** 的 **“安全”** 页上启用了部分信任安全。 有关详细信息，请参阅[如何： 调试部分信任应用程序](../debugger/how-to-debug-a-partial-trust-application.md)。

## <a name="design-time-expression-evaluation"></a>设计时表达式计算
 设计时表达式始终使用宿主进程。 如果在 **“项目属性”** 中禁用宿主进程，则禁用了类库项目的设计时表达式计算。 对于其他项目类型，不禁用设计时表达式计算。 相反，Visual Studio 启动实际可执行文件，并将它用于不用宿主进程的设计时计算。 这种差异可能产生不同的结果。

## <a name="appdomaincurrentdomainfriendlyname-differences"></a>AppDomain.CurrentDomain.FriendlyName 差异
 `AppDomain.CurrentDomain.FriendlyName` 依据是否启用宿主进程返回不同的结果。 如果在启用宿主进程时调用 `AppDomain.CurrentDomain.FriendlyName` ，它将返回 *app_name*`.vhost.exe`。 如果在启用宿主进程时调用它，它将返回 *app_name*`.exe`。

## <a name="assemblygetcallingassemblyfullname-differences"></a>Assembly.GetCallingAssembly().FullName 差异
 `Assembly.GetCallingAssembly().FullName` 依据是否启用宿主进程返回不同的结果。 如果在启用宿主进程时调用 `Assembly.GetCallingAssembly().FullName` ，它将返回 `mscorlib`。 如果禁用宿主进程时调用 `Assembly.GetCallingAssembly().FullName` ，它将返回该应用程序名。

## <a name="see-also"></a>请参阅

- [如何：调试部分信任的应用程序](../debugger/how-to-debug-a-partial-trust-application.md)