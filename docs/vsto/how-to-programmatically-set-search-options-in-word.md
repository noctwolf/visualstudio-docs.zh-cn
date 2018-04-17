---
title: 如何： 以编程方式在 Word 中设置搜索选项 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- settings, Word search options
- documents [Office development in Visual Studio], search options
- Word, searching options
- searching, Word options
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3be8d12f18e4ea0b6d05cbad92c08c7b5427315c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-set-search-options-in-word"></a>如何：以编程方式在 Word 中设置搜索选项
  有两种方法在 Microsoft Office Word 文档中设置选择的搜索选项：  
  
-   设置各个属性<xref:Microsoft.Office.Interop.Word.Find>对象。  
  
-   使用的自变量<xref:Microsoft.Office.Interop.Word.Find.Execute%2A>方法<xref:Microsoft.Office.Interop.Word.Find>对象。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="using-properties-of-a-find-object"></a>使用查找对象的属性  
 下面的代码设置的属性<xref:Microsoft.Office.Interop.Word.Find>对象要搜索的当前选择的范围内的文本。 请注意搜索条件，如搜索进、 自动换行，以及文本来进行搜索，是的属性<xref:Microsoft.Office.Interop.Word.Find>对象。  
  
 设置每个属性的<xref:Microsoft.Office.Interop.Word.Find>对象不有用，因为你必须指定相同的属性中的参数一样编写 C# 代码时<xref:Microsoft.Office.Interop.Word.Find.Execute%2A>方法。 因此，本示例包含仅 Visual Basic 代码。  
  
#### <a name="to-set-search-options-using-a-find-object"></a>若要设置搜索选项使用查找对象  
  
1.  设置的属性<xref:Microsoft.Office.Interop.Word.Find>对象向前搜索文本的选择内容**找到我**。  
  
     [!code-vb[Trin_VstcoreWordAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#76)]  
  
## <a name="using-execute-method-arguments"></a>使用执行方法自变量  
 下面的代码使用<xref:Microsoft.Office.Interop.Word.Find.Execute%2A>方法<xref:Microsoft.Office.Interop.Word.Find>对象要搜索的当前选择的范围内的文本。 请注意，作为参数传递的搜索条件，如搜索进、 自动换行，以及文本来进行搜索，<xref:Microsoft.Office.Interop.Word.Find.Execute%2A>方法。  
  
#### <a name="to-set-search-options-using-execute-method-arguments"></a>若要设置搜索选项使用 Execute 方法自变量  
  
1.  将搜索条件作为参数传递<xref:Microsoft.Office.Interop.Word.Find.Execute%2A>方法以文本的选择内容中向前搜索**找到我**。  
  
     [!code-vb[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#77)]
     [!code-csharp[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#77)]  
  
## <a name="see-also"></a>请参阅  
 [如何： 以编程方式搜索和替换文档中的文本](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [如何： 以编程方式遍历在文档中找到的项](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [如何：以编程方式在搜索后还原选定内容](../vsto/how-to-programmatically-restore-selections-after-searches.md)  
  
  