---
title: 创建数据的自定义可视化工具 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.visualizer.troubleshoot
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, visualizers
- visualizers
ms.assetid: c24c006f-f2ac-429f-89db-677fc0c6e1ea
caps.latest.revision: 31
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a025068d1657d9feb569a77731aa8bab517bae2f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480211"
---
# <a name="create-custom-visualizers-of-data"></a>创建数据的自定义可视化工具
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[的数据创建自定义可视化工具](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)。  
  
可视化工具是组件的[!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)]调试器用户界面。 一个*可视化工具*创建对话框或另一个接口，以适合于其数据类型的方式显示变量或对象。 例如，HTML 可视化工具解释 HTML 字符串，并按照该字符串出现在浏览器窗口中时的样子显示结果；位图可视化工具解释位图结构并显示该位图结构表示的图形。 某些可视化工具允许您修改数据，还允许您查看数据。  
  
 [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] 调试器包括六个标准可视化工具。 这些是文本、 HTML、 XML 和 JSON 可视化工具，所有这些处理字符串对象;WPF 树可视化工具，用于显示 WPF 对象可视化树; 的属性和数据集可视化工具，一种用于 DataSet、 DataView 和 DataTable 对象。 将来可以从 Microsoft Corporation 以及第三方和社区下载更多的可视化工具。 此外，你可以编写自己的可视化工具，并将它们安装在 [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] 调试器中。  
  
> [!NOTE]
>  在中**Store**应用，仅在标准文本支持 HTML、 XML 和 JSON 可视化工具。 不支持自定义（用户创建的）可视化工具。  
  
 可视化工具在调试器中用放大镜图标表示。 请参阅中的放大镜图标时**数据提示**、 在调试器变量窗口中，或在**快速监视**对话框中，可以单击该放大镜以选择适合于数据类型的可视化工具相应的对象。  
  
 Compact Framework 上不支持可视化工具。  
  
> [!NOTE]
>  调试器可视化工具要求比部分信任的应用程序允许的特权更大的特权。 因此，在部分信任的代码中停止时，可视化工具不会加载。 若要使用可视化工具进行调试，必须运行完全信任的代码。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：编写可视化工具](../debugger/how-to-write-a-visualizer.md)  
  
 [演练：用 C# 编写可视化工具](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)  
  
 [如何：安装可视化工具](../debugger/how-to-install-a-visualizer.md)  
  
 [如何：测试和调试可视化工具](../debugger/how-to-test-and-debug-a-visualizer.md)  
  
 [可视化工具 API 参考](../debugger/visualizer-api-reference.md)  
  
## <a name="related-sections"></a>相关章节  
 [查看调试器中的数据](../debugger/viewing-data-in-the-debugger.md)



