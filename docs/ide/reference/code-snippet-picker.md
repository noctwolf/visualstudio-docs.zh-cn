---
title: "代码片段选择器 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.expansionpicker
helpviewer_keywords:
- Code Snippet Picker
- IntelliSense code snippets, Code Snippet Picker
- code snippets, Code Snippet Picker
ms.assetid: f0862d48-fbbc-4cfe-b228-24492d5c89c4
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e352baf834f026462cb35921f7f79e75b3aecd96
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="code-snippet-picker"></a>代码段选择器
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 代码编辑器提供了“代码片段选择器”，使用它，单击几下鼠标就可将现成的代码块插入到活动文档中。  
  
 显示“代码片段选择器”的过程根据用户所使用的语言会有所不同。  
  
-   [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]：在代码编辑器中所需的位置处右击，以显示快捷菜单，然后选择“插入片段”。  
  
-   [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]：在代码编辑器中所需的位置处右击，以显示快捷菜单，然后单击“插入片段”或“外侧代码”。  
  
-   [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]：“代码片段选择器”不可用。  
  
-   Visual F#：“代码片段选择器”不可用。  
  
-   [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)]：在代码编辑器中所需的位置处右击，以显示快捷菜单，然后单击“插入片段”或“外侧代码”。  
  
-   XML：在代码编辑器中所需的位置处右击，以显示快捷菜单，然后单击“插入片段”或“外侧代码”。  
  
-   HTML：在代码编辑器中所需的位置处右击，以显示快捷菜单，然后单击“插入片段”或“外侧代码”。  
  
-   SQL：在代码编辑器中所需的位置处右击，以显示快捷菜单，然后单击“插入片段”。  
  
在大多数 Visual Studio 开发语言中，可以使用“代码片段管理器”将文件夹添加到“文件夹列表”，“代码片段选择器”会在该列表中扫描 XML 片段文件。 也可以创建自己的片段添加到该列表。 有关详细信息，请参阅[演练：创建代码片段](../../ide/walkthrough-creating-a-code-snippet.md)。  
  
## <a name="uielement-list"></a>UIElement 列表  
项名称  
可编辑文本字段，显示在“项列表”中选定的项的名称。 若要执行渐进式搜索以查找所需的项，请首先在此字段中键入其名称。 继续添加字母，直到在“项列表”中选定所需的项。  
  
项列表  
可以插入的代码片段的列表，或包含代码片段的文件夹的列表。 若要插入片段或展开文件夹，请选择所需的项，然后按 Enter。  
  
## <a name="see-also"></a>请参阅  
[有关使用代码片段的最佳做法](../../ide/best-practices-for-using-code-snippets.md)   
[Visual Basic IntelliSense 代码片段](/dotnet/visual-basic/developing-apps/using-ide/intellisense-code-snippets)   
[在代码中设置书签](../../ide/setting-bookmarks-in-code.md)   
[如何：使用外侧代码片段](../../ide/how-to-use-surround-with-code-snippets.md)