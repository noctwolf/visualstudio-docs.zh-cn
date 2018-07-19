---
title: 如何： 以编程方式打开现有文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], opening
- Word [Office development in Visual Studio], opening documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: dd9e120283c392978a21fa9f796f9eed5e3dab31
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258718"
---
# <a name="how-to-programmatically-open-existing-documents"></a>如何： 以编程方式打开现有文档
  <xref:Microsoft.Office.Interop.Word.Documents.Open%2A>方法打开指定的完全限定的路径和文件名称的现有 Microsoft Office Word 文档。 此方法返回<xref:Microsoft.Office.Interop.Word.Document>表示打开的文档。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-open-a-document"></a>若要打开的文档  
  
-   调用<xref:Microsoft.Office.Interop.Word.Documents.Open%2A>方法的<xref:Microsoft.Office.Interop.Word.Documents>集合并提供对文档的路径。  
  
     [!code-vb[Trin_VstcoreWordAutomation#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#5)]
     [!code-csharp[Trin_VstcoreWordAutomation#5](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#5)]  
  
## <a name="to-open-a-document-as-read-only"></a>若要打开的文档为只读的  
  
-   调用<xref:Microsoft.Office.Interop.Word.Documents.Open%2A>方法，提供的文档路径，并设置*ReadOnly*自变量**True**方法调用中。  
  
     [!code-vb[Trin_VstcoreWordAutomation#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#6)]
     [!code-csharp[Trin_VstcoreWordAutomation#6](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#6)]  
  
## <a name="compile-the-code"></a>编译代码  
 此代码示例要求满足以下条件：  
  
-   名为的文档*NewDocument.doc*必须存在于一个名为目录*测试*在驱动器 c。  
  
## <a name="see-also"></a>请参阅  
 [如何： 以编程方式创建新的文档](../vsto/how-to-programmatically-create-new-documents.md)   
 [如何： 以编程方式关闭文档](../vsto/how-to-programmatically-close-documents.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)  
  
  