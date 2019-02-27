---
title: 创建对象的自定义视图 |Microsoft Docs
ms.date: 01/08/2019
ms.topic: conceptual
f1_keywords:
- vs.debug.data.elements
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data types, custom
- custom data types
- managed code, custom data types
- autoexp.dat file
- mcee_cs.dat file
- debugger, expanding data types
- mcee_mc.dat file
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 748305683ad8f874c985e2599028152d608ccc84
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56597411"
---
# <a name="create-custom-views-of-objects-c-visual-basic-c"></a>创建自定义视图的对象 (C#，Visual Basic、 c + +)
可以在调试器变量窗口中自定义 Visual Studio 显示数据类型的方式。

## <a name="native-code"></a>本机代码

对于 c + + 代码中，您可以添加自定义数据类型扩展使用 Natvis 框架，如中所述[在调试器中创建本机对象的自定义视图](/visualstudio/debugger/create-custom-views-of-native-objects)。 对于 C + + /cli CLI 代码中，您还可以使用本文中的此处所述的特性。

## <a name="attributes"></a>特性

在C#，Visual Basic 和 c + + (C + + CLI 代码仅限)，可以添加自定义数据使用的扩展<xref:System.Diagnostics.DebuggerTypeProxyAttribute>， <xref:System.Diagnostics.DebuggerDisplayAttribute>，并<xref:System.Diagnostics.DebuggerBrowsableAttribute>。

在 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] 代码中，Visual Basic 不支持 DebuggerBrowsable 特性。 此项限制在 .NET Framework 较高版本中已经删除。

## <a name="visualizers"></a>可视化工具

可以编写可视化工具来显示任何托管数据类型。 有关详细信息，请参阅[如何： 编写可视化工具](/visualstudio/debugger/create-custom-visualizers-of-data)。

## <a name="see-also"></a>请参阅

- [使用 DebuggerTypeProxy 特性](../debugger/using-debuggertypeproxy-attribute.md)
- [使用 DebuggerDisplay 特性](../debugger/using-the-debuggerdisplay-attribute.md)
- [监视和快速监视窗口](../debugger/watch-and-quickwatch-windows.md)
- [使用调试器显示特性增强调试](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)