---
title: "生成适用于 Visual Basic 的 XML 文档注释 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2f421553657dfafb265140e44e38a2c7722a7303
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2018
---
# <a name="generate-xml-documentation-comments-in-visual-basic"></a>在 Visual Basic 中生成 XML 文档注释

功能：快速生成记录选定元素所需的基本 XML。 

时机：想要使用 Sandcastle 等文档工具创建 XML 文档注释以供进行后续处理。

原因：可以自己手动创建整个注释块，但此功能可生成基本模板和其他元素，从而节约时间并提高准确性。 

方法：

1. 将文本光标放在要记录的元素上（例如，一种方法）。

   ![要记录的方法](media/doc-highlight-vb.png)

1. 接下来，键入“'''”（3 个单引号），此操作将在必要时自动创建基本模板和任何其他元素。  例如，注释方法时，它将为传递给此方法的每个参数生成 \<summary\> 标记和 \<param\> 标记，并生成 \<returns\> 标记来记录此方法返回的内容。

   ![模板](media/doc-preview-vb.png)

1. 完成注释并添加任何其他必要信息。

   ![完成的注释](media/doc-result-vb.png)

## <a name="see-also"></a>请参阅

[使用 XML 将代码文档化 (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml)  
[代码生成](../code-generation-in-visual-studio.md)