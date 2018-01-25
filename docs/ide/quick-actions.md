---
title: "快速操作 | Microsoft Docs"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.workload: multiple
ms.openlocfilehash: 259e033aa32caaca59f37d7dc77ac095b4709878
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="quick-actions"></a>快速操作

通过快速操作，只凭单个操作便可轻松重构、生成或修改代码。 快速操作可用于 C#、[C++](/cpp/ide/writing-and-refactoring-code-cpp) 和 Visual Basic 代码文件。 某些操作特定于一种语言，而其他操作适用于所有语言。

可使用灯泡图标![小灯泡图标](media/vs2015_lightbulbsmall.png)或按“Ctrl”+**应用快速操作。** 前提是光标位于相应的代码行上。 如果有红色波形曲线，则将看到灯泡，Visual Studio 针对如何解决此问题有一条建议。 例如，如果你遇到红色波形曲线指示的错误，则在可对该错误进行修复时，会显示灯泡。

对于任何语言，第三方均可提供自定义诊断和建议（例如，作为 SDK 的一部分），Visual Studio 电灯泡会根据这些规则亮起。

## <a name="to-see-a-light-bulb"></a>查看电灯泡

1. 在许多情况下，灯泡会在你将鼠标指针悬停在错误点上方时，或是在你将插入点移动到存在错误的行中时在编辑器左边距处自然而然地出现。 看到红色波形曲线时，可悬停在其上方，以显示电灯泡。 使用鼠标或键盘转到问题发生的行时，也会显示电灯泡。

1. 按“Ctrl”+**。** 可调用电灯泡并直接转到潜在修复列表。

   ![带鼠标悬停的灯泡](../ide/media/vs2015_lightbulb_hover.png "VS2017_LightBulb_Hover")

## <a name="to-see-potential-fixes"></a>查看潜在修复

单击向下箭头或“显示潜在修复”链接，以显示电灯泡可执行的快速操作列表。

![灯泡已展开](../ide/media/vs2015_lightbulb_hover_expanded.png "VS2017_LightBulb_hover_expanded")

## <a name="see-also"></a>请参阅

[Visual Studio 中的代码生成](../ide/code-generation-in-visual-studio.md)  
[常见快速操作](../ide/common-quick-actions.md)  
[代码样式和快速操作](../ide/code-styles-and-quick-actions.md)  
[编写和重构代码 (C++)](/cpp/ide/writing-and-refactoring-code-cpp)