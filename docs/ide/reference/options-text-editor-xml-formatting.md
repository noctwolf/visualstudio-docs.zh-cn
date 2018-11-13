---
title: 选项, 文本编辑器, XML, 格式设置
ms.date: 10/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Formatting
ms.assetid: 203e60b2-7b80-4ff4-9fa1-aa9f4374377b
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 1af8ff6f085d744cb58cb3844fced18d3e484494
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50673207"
---
# <a name="options-text-editor-xml-formatting"></a>选项, 文本编辑器, XML, 格式设置
使用“格式设置”属性页以指定如何在 XML 文档中设置元素和特性的格式。 若要打开“选项”对话框，请单击“工具”菜单，然后单击“选项”。 要访问“格式设置”属性页，请展开“文本编辑器” > “XML” > “格式设置”节点。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)。

## <a name="attributes"></a>特性  
**保留手动特性格式设置**  
请勿重新设置特性的格式。 此设置为默认设置。  
  
> [!NOTE]  
>  如果属性在多行上，编辑器将对每行属性进行缩进，以便与父元素的缩进匹配。  
  
**在单独的行上对齐每个特性**  
使第二个以及后续的特性纵向对齐，以便与第一个特性的缩进匹配。 以下 XML 文本是如何对齐特性的示例。  
  
```xml
<item id = "123-A"  
      name = "hammer"  
      price = "9.95"  
</item>  
```  
  
## <a name="auto-reformat"></a>自动重新设置格式  
**从剪贴板粘贴时**  
重新设置从剪贴板粘贴的 XML 文本的格式。  
  
**完成结束标记时**  
在完成结束标记时重新设置元素的格式。  
  
## <a name="mixed-content"></a>混合内容  
**默认设置混合内容的格式。**  
将尝试重新设置混合内容的格式，除非在 `xml:space="preserve"` 范围内找到该内容。 此设置为默认设置。  
  
如果元素中包含文本和标记的混合，将认为内容是混合内容。 以下是包含混合内容的元素示例。  
  
```xml
<dir>c:\data\AlphaProject\  
  <file readOnly="false">test1.txt</file>  
  <file readOnly="false">test2.txt</file>  
\</dir>  
```  
## <a name="see-also"></a>请参阅
- [如何创建 XML 文档 (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation)
- [代码生成](../code-generation-in-visual-studio.md)
  
