---
title: 如何： 以编程方式从文档中删除所有注释
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], removing comments
- comments, removing from documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 005414fce7b7bc04c22b266f5f5f6d54a399a182
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "35670606"
---
# <a name="how-to-programmatically-remove-all-comments-from-documents"></a>如何： 以编程方式从文档中删除所有注释
  使用`DeleteAllComments`方法以从 Microsoft Office Word 文档中删除所有注释。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-remove-all-comments-from-a-document-that-is-part-of-a-document-level-customization"></a>从属于文档级自定义项的文档中删除所有注释  
  
1.  调用项目中 <xref:Microsoft.Office.Tools.Word.Document.DeleteAllComments%2A> 类的 `ThisDocument` 方法。 若要使用此代码示例，请从 `ThisDocument` 类中运行它。  
  
     [!code-vb[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomation#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#119)]  
  
## <a name="to-remove-all-comments-from-a-document-by-using-a-vsto-add-in"></a>若要通过使用 VSTO 外接程序从文档中删除所有注释  
  
1.  调用要从中删除注释的 <xref:Microsoft.Office.Interop.Word._Document.DeleteAllComments%2A> 的 <xref:Microsoft.Office.Interop.Word.Document> 方法。  
  
     下面的代码示例从活动文档中删除所有注释。 若要使用此代码示例，请从项目中的 `ThisAddIn` 类运行它。  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#119)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#119](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#119)]  
  
## <a name="see-also"></a>请参阅  
 [如何： 以编程方式向文档中的文本添加注释](../vsto/how-to-programmatically-add-comments-to-text-in-documents.md)   
 [文档主机项](../vsto/document-host-item.md)  
  
  