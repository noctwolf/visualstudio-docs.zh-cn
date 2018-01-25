---
title: "在 Visual Studio 中重命名文件名以匹配 C# 类型 | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: CSharp
ms.workload: dotnet
ms.openlocfilehash: ada7044ebb6718dc0380b387a130ea7b2334e443
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-in-c"></a>在 C# 中同步类型到文件名或同步文件名到类型 #

<!-- VERSIONLESS -->
**此功能在 Visual Studio 2017 及更高版本中提供。此外，该重构尚不支持 .NET 标准项目。**

功能：重命名类型以匹配文件名，或重命名文件名以匹配其包含的类型。

时机：已重命名文件或类型，且尚未更新相应文件或类型进行匹配时。 

原因：将类型置于具有其他名称的文件中，将很难查找要搜索的内容，反之亦然。  通过重命名类型或文件名，代码变得更具可读性且更易于导航。

方法：

1. 突出显示要同步的类型名称，或将文本光标置于其中：

   ![突出显示的代码](media/synctype-highlight-cs.png)

1. 接下来，执行以下操作之一：
   * **键盘**
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“重命名文件为 TypeName.cs”，其中“TypeName”是已选定的类型名称。
     * 按“Ctrl+.” 触发“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“重命名类型为 _Filename_”，其中“Filename”是当前文件名。
   * **鼠标**
     * 右键单击代码，选择“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“重命名文件为 TypeName.cs”，其中“TypeName”是已选定的类型名称。
     * 右键单击代码，选择“快速操作和重构”菜单，然后从“预览”弹出窗口中选择“重命名类型为 _Filename_”，其中“Filename”是当前文件名。

   将立即重命名类型或文件。  在以下示例中，文件“MyClass.cs”被重命名为“MyNewClass.cs”以匹配类型名称。

   ![内联结果](media/synctype-result-cs.png)

## <a name="see-also"></a>请参阅

[重构](../refactoring-in-visual-studio.md)
