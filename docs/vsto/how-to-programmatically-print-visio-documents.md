---
title: 如何： 以编程方式打印 Visio 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], printing Visio documents
- documents [Office development in Visual Studio], printing Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4caf48d0268e653b7ce6f7a5c8e7efb1e2ec39e6
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257500"
---
# <a name="how-to-programmatically-print-visio-documents"></a>如何： 以编程方式打印 Visio 文档
  你可以打印完整的 Microsoft Office Visio 文档或仅打印某一特定页。  
  
 有关打印方法的详细信息，请参阅 [Microsoft.Office.Interop.Visio.Document.Print](https://msdn.microsoft.com/library/office/ff767996.aspx) 方法和 [Microsoft.Office.Interop.Visio.Page.Print](https://msdn.microsoft.com/library/office/ff765064.aspx) 方法的 VBA 参考文档。  
  
## <a name="print-a-visio-document"></a>打印 Visio 文档  
  
### <a name="to-print-a-complete-document"></a>打印完整的文档  
  
-   调用`Microsoft.Office.Interop.Visio.Document.Print`方法的`Microsoft.Office.Interop.Visio.Document`您想要打印的对象。  
  
     下面的代码示例将打印活动文档。 若要使用此示例，请从项目的 `ThisAddIn` 类中运行代码。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#8)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#8)]  
  
## <a name="print-a-page-of-a-visio-document"></a>打印 Visio 文档的一页  
  
### <a name="to-print-a-page-of-a-document"></a>打印文档的某一页  
  
-   调用`Microsoft.Office.Interop.Visio.Pages.Print`方法的`Microsoft.Office.Interop.Visio.Pages`您想要打印的对象。  
  
     下面的代码示例打印活动文档的第一页。 若要使用此示例，请从项目的 `ThisAddIn` 类中运行代码。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>请参阅  
 [Visio 解决方案](../vsto/visio-solutions.md)   
 [Visio 对象模型概述](../vsto/visio-object-model-overview.md)   
 [如何： 以编程方式创建新的 Visio 文档](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [如何： 以编程方式打开 Visio 文档](../vsto/how-to-programmatically-open-visio-documents.md)   
 [如何： 以编程方式关闭 Visio 文档](../vsto/how-to-programmatically-close-visio-documents.md)   
 [如何： 以编程方式保存 Visio 文档](../vsto/how-to-programmatically-save-visio-documents.md)  
  
  