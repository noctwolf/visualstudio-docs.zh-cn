---
title: 选项, 文本编辑器, XML, 杂项
ms.date: 10/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Miscellaneous
ms.assetid: b6538cbe-badd-4313-a1fb-39e906736bbe
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: c6def0a2e374e5297d25d17f4ea4a4a113d4bd56
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50673215"
---
# <a name="options-text-editor-xml-miscellaneous"></a>选项, 文本编辑器, XML, 杂项
使用“杂项”属性页更改 XML 编辑器的自动完成和架构设置。 若要打开“选项”对话框，请单击“工具”菜单，然后单击“选项”。 要访问“杂项”属性页，请展开“文本编辑器” > “XML” > “杂项”节点。

> [!NOTE]
> 显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)。

## <a name="auto-insert"></a>自动插入  
**结束标记**  
创作 XML 元素时，文本编辑器将添加结束标记。 如果选择了元素开始标记，则编辑器会插入匹配的结束标记，包括匹配的命名空间前缀。 默认情况下选中此复选框。  
  
**特性引号**  
在创作 XML 属性时，编辑器会插入 `="` 和 `"` 字符并将插入符号 (^) 置于引号之间。 默认情况下选中此复选框。  
  
**命名空间声明**  
编辑器根据需要自动插入命名空间声明。 默认情况下选中此复选框。  
  
**其他标记（注释、CDATA）**  
自动完成注释、CDATA、DOCTYPE、处理指令和其他标记。 默认情况下选中此复选框。  
  
## <a name="network"></a>网络  
**自动下载 DTD 和架构**  
架构和文档类型定义 (DTD) 自动从 HTTP 位置下载。 此功能在自动代理服务器检测启用的情况下使用 System.Net。 默认情况下选中此复选框。  
  
## <a name="outlining"></a>大纲显示  
**打开文件时进入大纲模式**  
在打开文件时启用大纲功能。 默认情况下选中此复选框。  
  
## <a name="caching"></a>缓存  
**架构**  
指定架构缓存的位置。 “浏览”按钮 (...) 在新窗口中打开当前架构的缓存位置。 默认位置为 \<Management Studio 安装目录>\Xml\Schemas。  
  
## <a name="see-also"></a>请参阅
- [如何创建 XML 文档 (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation)
- [代码生成](../code-generation-in-visual-studio.md)
