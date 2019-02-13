---
title: 自动换行
ms.date: 11/07/2018
ms.topic: conceptual
helpviewer_keywords:
- word wrap
- editors, text viewing
- Code Editor, word wrap
ms.assetid: 442f33ef-9f52-4515-b55f-fb816d664645
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 88d5b4729ec24ef9594e3c0528a8d09156f23b1b
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55926264"
---
# <a name="how-to-manage-word-wrap-in-the-editor"></a>如何：在编辑器中管理自动换行

可以设置和清除“自动换行”选项。 如果设置了此选项，较长行中超出代码编辑器窗口当前宽度的部分将在下一行显示。 如果清除了此选项，例如，为方便使用行号，则可以向右滚动查看较长行的末尾。

> [!NOTE]
> 本主题仅适用于 Windows 上的 Visual Studio。 Visual Studio for Mac 目前不支持自动换行。

## <a name="to-set-word-wrap-preferences"></a>设置换行首选项

1.  在“工具”菜单上选择“选项”。

2.  在“文本编辑器”文件夹的“所有语言”子文件夹中选择“常规”选项，在全局设置此选项。

     — 或 —

     在编程所用的语言的子文件夹中选择“常规”选项。

3.  在“设置”下，选择或清除“自动换行”选项。

     选中“自动换行”选项将启用“显示可视的自动换行标志符号”选项。

4.  如果希望在较长行换行到下一行的位置处显示回车箭头指示符，请选择“显示可视的自动换行标志符号”选项。 如果不希望显示这些指示箭头，则清除此复选框。

    > [!NOTE]
    > 这些提醒箭头不会添加到代码中，它们仅用于显示。

## <a name="known-issues"></a>已知问题

如果熟悉 Notepad++、Sublime Text 或 Visual Studio Code 中的自动换行功能，请注意 Visual Studio 的行为在以下方面与其他编辑器的行为不同：

* [三次单击不会选择整行](https://developercommunity.visualstudio.com/content/problem/268989/triple-click-doesnt-select-whole-line-when-word-wr.html)
* [剪切命令不会删除整行](https://developercommunity.visualstudio.com/content/problem/138259/cut-command-should-delete-logical-line.html)
* [按两次 End 键不会将光标移动到行尾](https://developercommunity.visualstudio.com/content/problem/138274/pressing-end-key-twice-should-move-cursor-to-end-o.html)

## <a name="see-also"></a>请参阅

- [自定义编辑器](../../ide/customizing-the-editor.md)
- [“选项”对话框 ->“文本编辑器”](../../ide/reference/text-editor-options-dialog-box.md)
- [代码编辑器功能](../../ide/writing-code-in-the-code-and-text-editor.md)
