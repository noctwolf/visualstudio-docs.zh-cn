---
title: "Visual Studio 中的代码生成功能 | Microsoft Docs"
ms.custom: 
ms.date: 01/11/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 7740fcea4ac944242f4284382cf26544d9ea95b5
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="code-generation-features-in-visual-studio"></a>Visual Studio 中的代码生成功能

在编辑器中，有多种借助 Visual Studio 生成代码的方法。 通过使用这些代码生成功能，可以节省时间和按键，减少语法错误，并提升代码的一致性。

Visual Studio 中可生成代码的部分功能包括[代码片段](../ide/code-snippets.md)和[快速操作](../ide/quick-actions.md)![小灯泡图标](media/vs2015_lightbulbsmall.png)。

通过[快速操作](../ide/quick-actions.md)提供的一些常见的代码生成任务包括：

* 生成类、方法和属性等。

* 实现抽象类或接口

* 将本地变量引入复杂表达式

此外，通过键入某些字符，可以：

* 为代码生成 [XML 格式的注释块]()，稍后可对其进行处理以自动生成文档。

* 生成[方法重写]()签名

因为代码生成的逻辑与语言语法密切相关，所以 Visual Studio 中的每个语言服务都会提供自己的代码生成功能。

## <a name="see-also"></a>请参阅

[快速操作](../ide/quick-actions.md)  
[代码片段](../ide/code-snippets.md)  
[代码生成和 T4 文本模板](../modeling/code-generation-and-t4-text-templates.md)  
[重构](../ide/refactoring-in-visual-studio.md)