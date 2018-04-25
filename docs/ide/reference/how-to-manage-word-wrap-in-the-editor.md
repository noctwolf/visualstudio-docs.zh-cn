---
title: 如何：在编辑器中管理自动换行 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- word wrap
- editors, text viewing
- Code Editor, word wrap
ms.assetid: 442f33ef-9f52-4515-b55f-fb816d664645
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: edd81a4c4168d7733b21ec84123e984e42b71063
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-manage-word-wrap-in-the-editor"></a>如何：在编辑器中管理自动换行

可以设置和清除“自动换行”选项。 如果设置了此选项，较长行中超出代码编辑器窗口当前宽度的部分将在下一行显示。 如果清除了此选项，例如，为方便使用行号，则可以向右滚动查看较长行的末尾。

> [!NOTE]
> 显示的对话框和菜单命令可能与“帮助”中的描述不同，具体取决于现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)。

## <a name="procedure"></a>过程

### <a name="to-set-word-wrap-preferences"></a>设置换行首选项
  
1.  在“工具”菜单上选择“选项”。  
  
2.  在“文本编辑器”文件夹的“所有语言”子文件夹中选择“常规”选项，在全局设置此选项。  
  
     — 或 —  
  
     在编程所用的语言的子文件夹中选择“常规”选项。  
  
3.  在“设置”下，选择或清除“自动换行”选项。  
  
     选中“自动换行”选项将启用“显示可视的自动换行标志符号”选项。  
  
4.  如果希望在较长行换行到下一行的位置处显示回车箭头指示符，请选择“显示可视的自动换行标志符号”选项。 如果不希望显示这些指示箭头，则清除此复选框。  
  
    > [!NOTE]
    >  这些提醒箭头不会添加到代码中：它们仅用于显示。  
  
## <a name="see-also"></a>请参阅

[自定义编辑器](../../ide/customizing-the-editor.md)  
[“选项”对话框 ->“文本编辑器”](../../ide/reference/text-editor-options-dialog-box.md)  
[编写代码](../../ide/writing-code-in-the-code-and-text-editor.md)