---
title: "生成 XML 文档注释 - 代码生成 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2025bd2-5984-4486-a61c-0a0933a735ea
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: b0a0ec1db54f57e14ddd412248f7a396336fe009
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="generate-xml-documentation-comments-in-c"></a>生成 XML 文档注释 (C#) #
功能：快速生成记录选定元素所需的基本 XML。 

时机：想要使用 Sandcastle 等文档工具创建 XML 文档注释以供进行后续处理。

原因：可以自己手动创建整个注释块，但此功能可生成基本模板和其他元素，从而节约时间并提高准确性。 

方法：

1. 将文本光标放在要记录的元素上（例如，一种方法）。

   ![要记录的方法](media/doc-highlight-cs.png)

1. 接下来，键入 **///**（3 个正斜杠），此操作将在必要时自动创建基本模板和任何其他元素。  例如，注释方法时，它将为传递给此方法的每个参数生成 \<summary\> 标记和 \<param\> 标记，并生成 \<returns\> 标记来记录此方法返回的内容。

   ![模板](media/doc-preview-cs.png)

1. 完成注释并添加任何其他必要信息。

   ![完成的注释](media/doc-result-cs.png)

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)  
[XML 文档注释（C# 编程指南）](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
