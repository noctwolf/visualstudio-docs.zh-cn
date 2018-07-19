---
title: 如何： 以编程方式复制和粘贴 Visio 文档中的形状
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- shapes [Office development in Visual Studio], copying and pasting Visio shapes
- Visio [Office development in Visual Studio], copying and pasting Visio shapes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 29dada62bb1e51c9cafb41d4eae08ce10e9a930c
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257080"
---
# <a name="how-to-programmatically-copy-and-paste-shapes-in-a-visio-document"></a>如何： 以编程方式复制和粘贴 Visio 文档中的形状
  你可以以编程方式复制文档中某一页上的形状，并将其粘贴到同一文档中新的一页。 你可以选择将其粘贴到默认位置（活动窗口的中央），或将其粘贴到与在其原始页相同的坐标位置。  
  
## <a name="copy-and-paste-shapes"></a>复制和粘贴形状  
 有关对象模型的详细信息，请参阅 [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](https://msdn.microsoft.com/library/office/ff765757.aspx)、 [Microsoft.Office.Interop.Visio.Shape.DrawOval](https://msdn.microsoft.com/library/office/ff767121.aspx)、 [Microsoft.Office.Interop.Visio.Shape.Copy](https://msdn.microsoft.com/library/office/ff765638.aspx)和 [Microsoft.Office.Interop.Visio.Shape.Paste](https://msdn.microsoft.com/library/office/ff768361.aspx) 方法以及 [Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNormal](https://msdn.microsoft.com/library/office/ff765187.aspx) 标志的 VBA 参考文档。  
  
### <a name="to-copy-shapes-to-the-center-of-another-page"></a>将形状复制到另一页的中央  
  
-   下面的示例演示如何复制第一页中的形状并将其粘贴到第二页的中央。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#14)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#14)]  
  
## <a name="copy-and-paste-shapes-with-the-same-positions"></a>复制和粘贴形状相同的位置  
 有关对象模型的详细信息，请参阅 [Microsoft.Office.Interop.Visio.Shape.DrawRectangle](https://msdn.microsoft.com/library/office/ff765757.aspx)、 [Microsoft.Office.Interop.Visio.Shape.DrawOval](https://msdn.microsoft.com/library/office/ff767121.aspx)、 [Microsoft.Office.Interop.Visio.Shape.Copy](https://msdn.microsoft.com/library/office/ff765638.aspx)和 [Microsoft.Office.Interop.Visio.Shape.Paste](https://msdn.microsoft.com/library/office/ff768361.aspx) 方法以及 [Microsoft.Office.Interop.Visio.VisCutCopyPasteCodes.visCopyPasteNoTranslate](https://msdn.microsoft.com/library/office/ff765187.aspx) 标志的 VBA 参考文档。  
  
 如果需要控制所粘贴信息的格式和 （可选） 建立到源文件 （例如，Microsoft Office Word 文档） 的链接，使用 PasteSpecial 方法。  
  
### <a name="to-copy-shapes-and-shape-locations-to-another-page"></a>将形状和形状位置复制到另一页  
  
-   下面的示例演示如何复制第一页中的形状并将其粘贴到第二页中与其原始坐标相同的位置。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#15)]  
  
## <a name="see-also"></a>请参阅  
 [Visio 解决方案](../vsto/visio-solutions.md)   
 [Visio 对象模型概述](../vsto/visio-object-model-overview.md)   
 [使用 Visio 形状](../vsto/working-with-visio-shapes.md)   
 [如何： 以编程方式向 Visio 文档添加形状](../vsto/how-to-programmatically-add-shapes-to-a-visio-document.md)  
  
  