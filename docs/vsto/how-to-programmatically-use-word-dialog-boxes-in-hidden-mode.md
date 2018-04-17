---
title: 如何： 以编程方式使用 Word 对话框在隐藏模式下 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden dialog boxes
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, hidden mode in Word
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7b9d9b49783e3070e91291460e3f4aa7a4667620
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-use-word-dialog-boxes-in-hidden-mode"></a>如何：以编程方式在隐藏模式下使用 Word 对话框
  可以通过调用 Microsoft Office Word 中的内置对话框而不向用户显示它们来执行复杂的操作通过一个方法调用。 你可以执行此操作通过使用<xref:Microsoft.Office.Interop.Word.Dialog.Execute%2A>方法<xref:Microsoft.Office.Interop.Word.Dialog>对象而不调用<xref:Microsoft.Office.Interop.Word.Dialog.Display%2A>方法。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="examples"></a>示例  
 下面的代码示例演示如何使用**页面设置**在隐藏模式下以无用户输入的设置多个页面设置属性对话框。 示例使用<xref:Microsoft.Office.Interop.Word.Dialog>对象配置的自定义的页大小。 页面设置，如上边距、 下边距和等等的特定设置都可用作后期绑定属性的<xref:Microsoft.Office.Interop.Word.Dialog>对象。 在运行时中，这些属性通过 Word 动态创建。  
  
 下面的示例演示如何在 Visual Basic 项目中执行此任务其中**Option Strict**已关闭，且 Visual C# 项目中面向[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]。 在这些项目中，你可以在 Visual Basic 和 Visual C# 编译器中使用后期绑定功能。 若要使用此示例中，运行从`ThisDocument`或`ThisAddIn`项目中的类。  
  
 [!code-vb[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#123)]
 [!code-csharp[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#123)]  
  
 下面的示例演示如何在 Visual Basic 项目中执行此任务其中**Option Strict**上。 在这些项目中，你必须使用反射来访问后期绑定属性。 若要使用此示例中，运行从`ThisDocument`或`ThisAddIn`项目中的类。  
  
 [!code-vb[Trin_VstcoreWordAutomation#104](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#104)]  
  
## <a name="see-also"></a>请参阅  
 [如何： 以编程方式使用 Word 中的内置对话框](../vsto/how-to-programmatically-use-built-in-dialog-boxes-in-word.md)   
 [Word 对象模型概述](../vsto/word-object-model-overview.md)   
 [在 Office 解决方案中的后期绑定](../vsto/late-binding-in-office-solutions.md)   
 [反射 (C#)](/dotnet/csharp/programming-guide/concepts/reflection)  
 [反射 (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)  
  
  