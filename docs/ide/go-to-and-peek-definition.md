---
title: "转到定义和速览定义 | Microsoft Docs"
ms.custom: 
ms.date: 10/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code editor, go to definition
- code editor, peek definition
- go to definition
- peek definition
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 467d119e67db254b6e15630c08c411bb15283351
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="go-to-definition-and-peek-definition"></a>转到定义和速览定义  
“转到定义”和“速览定义”功能有助于轻松查看类型或成员的定义。

## <a name="go-to-definition"></a>转到定义  
“转到定义”功能可导航到类型或成员的源，并且在新选项卡中打开结果。如果使用键盘，请将文本游标放置在符号名称内部的某个位置，然后按 F12。 如果使用鼠标，请从上下文菜单选择“转到定义”或使用以下所述的“Ctrl + 单击”功能。  

### <a name="ctrl-click-go-to-definition"></a>Ctrl + 单击转到定义  
在 Visual Studio 2017 的 15.4 版本中，鼠标用户可以用更简单的方式快速访问转到定义。 按 Ctrl 并将鼠标悬停在类型或成员上，符号变为可单击。 要快速导航到某个符号的定义，按 Ctrl 键然后单击该符号。 就这么简单！

![鼠标单击转到定义动画](../ide/media/click_gotodef.gif)

前往“工具”->“选项”->“文本编辑器”->“常规”，然后从“使用修改键”下拉框中选择“Alt”或“Ctrl+Alt”，可以更改鼠标单击转到定义的修改键 。 取消选中“启用鼠标单击以执行转到定义”复选框还可以禁用鼠标单击转到定义。  

![启用鼠标单击转到定义](../ide/media/editor_options_mouse_click_gotodef.png)  

## <a name="peek-definition"></a>查看定义
“速览定义”功能有助于预览类型的定义，无需离开编辑器中的当前位置。 如果使用键盘，请将文本游标放置在类型或成员名称内的某个地方，然后按 Alt + F12。 如果使用鼠标，可以在上下文菜单中选择“预览定义”。 在 Visual Studio 2017 的 15.4 版本及更高版本中，使用鼠标快速查看定义可以采用新的方式。 首先，依次转到“工具”->“选项”->“文本编辑器”->“常规”。 选择“在速览视图中打开定义”选项然后单击“确定”关闭“选项”对话框。  

![设置鼠标单击速览定义选项](../ide/media/editor_options_peek_view.png)  

然后，按 Ctrl（或在“选项”中选中的任意一个修改键），然后单击类型或成员。  

![速览定义动画](../ide/media/peek_definition.gif)

如果在弹出式窗口中查看另一个定义，则将启动痕迹路径，即使用弹出式窗口上方显示的圆形菜单和箭头进行导航。  

有关详细信息，请参阅[如何：使用查看定义 (Alt+F12) 查看和编辑代码](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)。  

## <a name="see-also"></a>另请参阅  
[导航代码](../ide/navigating-code.md)  
[如何：使用查看定义 (Alt+F12) 查看和编辑代码](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)  
