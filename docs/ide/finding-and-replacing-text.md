---
title: 查找和替换文本
ms.date: 05/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.find
- vs.findreplacecontrol
- vs.findreplace.findsymbol
- vs.findreplace.symbol
- findresultswindow
- vs.findreplace.quickreplace
- vs.findsymbol
- vs.findinfiles
- vs.findresults1
- vs,findsymbolwindow
- vs.findreplace.quickfind
- vs.lookin
- vs.replace
helpviewer_keywords:
- text searches
- Replace in Files dialog box
- Find in Files dialog box
- text searches, finding and replacing text
- text, finding and replacing
- find and replace
- find text
- replace text
ms.assetid: a62545c3-1570-4d12-99fb-a82607eb35a1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7051b90dde45965b76e8a9e08b33b5326ff2848c
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="find-and-replace-text"></a>查找和替换文本

可以使用[查找和替换](#find-and-replace-control)或[在文件中查找/替换](#find-in-files-and-replace-in-files)，在 Visual Studio 编辑器中查找和替换文本。

> [!TIP]
> 如果要重命名代码符号（例如变量和方法），最好*[重构](../ide/reference/rename.md)* 它们，而不是使用查找和替换。 重构不仅智能而且知道应用范围，而查找和替换会盲目替换所有实例。

查找和替换功能在此编辑器中、其他某些基于文本的窗口（例如“查找结果”窗口）中、设计器窗口（如 XAML 设计器和 Windows 窗体设计器）中以及工具窗口中均提供。

可以将搜索范围限制到当前文档、当前解决方案或一组自定义文件夹中。 还可以指定一组文件扩展名，用于多文件搜索。 使用 .NET [正则表达式](../ide/using-regular-expressions-in-visual-studio.md)自定义搜索语法。

> [!TIP]
> [查找/命令](../ide/find-command-box.md)框可用作工具栏控件，但默认为不可见。 要显示“查找/命令”框，请在“标准”工具栏上选择“添加或删除按钮”，然后选择“查找”。

## <a name="find-and-replace-control"></a>“查找和替换”控件

“查找和替换”控件显示在代码编辑器窗口的右上角。 “查找和替换”控件会立即突出显示给定搜索字符串在当前文档中的每个匹配项。 通过在搜索控件上选择“查找下一个”按钮或“查找上一个”按钮，可以从一个匹配项导航到另一个匹配项。

![“查找和替换”控件](media/find-and-replace-box.png)

通过选择“查找”文本框旁边的按钮，可以访问替换选项。 若要一次替换一个，请选择“替换”文本框旁边的“替换下一个”按钮。 若要替换所有匹配项，请选择“全部替换”按钮。

若要更改匹配项的突出显示颜色，请依次选择“工具”菜单、“选项”、“环境”、“字体和颜色”。 在“显示设置对象”列表中，选择“文本编辑器”，然后在“显示项”列表中，选择“查找突出显示项(扩展名)”。

### <a name="search-tool-windows"></a>搜索工具窗口

通过选择“编辑” > “查找和替换”或按 Ctrl+F，可以在代码或文本窗口（如“输出”窗口和“查找结果”窗口）中使用“查找”控件。

某些工具窗口也提供某版本的“查找”控件。 例如，通过在搜索框中输入文本可以在“工具箱”窗口中筛选控件列表。 可以在其中搜索内容的其他工具窗口包括“解决方案资源管理器”、“属性”窗口和“团队资源管理器”。

## <a name="find-in-files-and-replace-in-files"></a>“在文件中查找”和“在文件中替换”

“在文件中查找/替换”与“查找和替换”控件类似，区别在于可以定义搜索范围。 不仅可以搜索当前在编辑器中打开的文件，还可以搜索所有打开的文档、整个解决方案、当前项目，及所选文件夹集。 还可以按文件扩展名搜索。 若要访问“在文件中查找/替换”对话框，请在“编辑”菜单上选择“查找和替换”，或按 Ctrl+Shift+F。

![“在文件中查找”对话框](media/find-in-files-box.png)

### <a name="find-results"></a>查找结果

选择“查找全部”后，“查找结果”窗口随即打开，并列出搜索的匹配项。 在列表中选择一个结果会显示相关联的文件，并突出显示匹配项。 如果文件尚未打开进行编辑，则可以在选项卡右侧的预览选项卡中打开。 可以使用“查找”控件在“查找结果”列表中搜索。

### <a name="create-custom-search-folder-sets"></a>创建自定义搜索文件夹集

通过选择“查找范围”框旁边的“选择搜索文件夹”按钮（类似于...），可以定义搜索范围。 在“选择搜索文件夹”对话框中，可以指定要搜索的一组文件夹，并且可以保存规范，供以后重复使用。

> [!TIP]
> 如果已将远程计算机的驱动器映射到本地计算机，则可以指定要在远程计算机上搜索的文件夹。

### <a name="create-custom-component-sets"></a>创建自定义组件集

通过选择“查找范围”框旁边的“编辑自定义组件集”按钮，可以将组件集定义为搜索范围。 可以指定已安装的 .NET 或 COM 组件，以及包含在解决方案或任何程序集或类型库（.dll、.tlb、.olb、.exe 或 .ocx）中的 Visual Studio 项目。 若要搜索引用，请选择“查找引用”框。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中使用正则表达式](../ide/using-regular-expressions-in-visual-studio.md)
- [在 Visual Studio 中重构代码](../ide/refactoring-in-visual-studio.md)