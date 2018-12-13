---
title: 如何： 以编程方式打开 Visio 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], opening Visio documents
- Visio [Office development in Visual Studio], opening Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 28f882510e2370c0fb31645da5023e865afd667e
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50672673"
---
# <a name="how-to-programmatically-open-visio-documents"></a>如何： 以编程方式打开 Visio 文档
  有两种方法打开现有的 Microsoft Office Visio 文档： 打开和 OpenEx。 OpenEx 方法等同于 Open 方法，只不过它提供调用方可以在其中指定文档打开方式的参数。  
  
 有关对象模型的详细信息，请参阅 [Microsoft.Office.Interop.Visio.Documents.Open](/office/vba/api/Visio.Documents.Open) 方法和 [Microsoft.Office.Interop.Visio.Documents.OpenEx](/office/vba/api/Visio.Documents.OpenEx) 方法的 VBA 参考文档。  
  
## <a name="open-a-visio-document"></a>打开 Visio 文档  
  
### <a name="to-open-a-visio-document"></a>若要打开 Visio 文档  
  
-   调用 `Microsoft.Office.Interop.Visio.Documents.Open` 方法并提供 Visio 文档的完全限定路径。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="open-a-visio-document-with-specified-arguments"></a>使用指定的参数打开 Visio 文档  
  
### <a name="to-open-a-visio-document-as-read-only-and-docked"></a>如要以只读和停靠方式打开 Visio 文档  
  
-   调用 `Microsoft.Office.Interop.Visio.Documents.OpenEx` 方法，提供 Visio 文档的完全限定路径，并包括想要使用的参数，在本例中为 Docked 和 Read-only。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#6)]  
  
## <a name="compile-the-code"></a>编译代码  
 此代码示例要求满足以下条件：  
  
-   名为的 Visio 文档`myDrawing.vsd`必须位于一个名为目录`Test`中*我的文档*文件夹 （对于 Windows XP 及更早版本） 或*文档*文件夹 （对于 Windows Vista)。  
  
## <a name="see-also"></a>请参阅  
 [Visio 解决方案](../vsto/visio-solutions.md)   
 [Visio 对象模型概述](../vsto/visio-object-model-overview.md)   
 [如何： 以编程方式创建新的 Visio 文档](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [如何： 以编程方式关闭 Visio 文档](../vsto/how-to-programmatically-close-visio-documents.md)   
 [如何： 以编程方式保存 Visio 文档](../vsto/how-to-programmatically-save-visio-documents.md)   
 [如何： 以编程方式打印 Visio 文档](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  