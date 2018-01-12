---
title: "如何： 以编程方式向 Visio 文档添加形状 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4d73c59ac9ba89a5814a264bb8e8fe3c83b9789e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>如何：以编程方式向 Visio 文档中添加形状
  可以通过从模具中检索主控形状并将形状放置在活动页面上，向 Microsoft Office Visio 文档添加形状。  
  
 有关详细信息，请参阅 [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) 方法、 [Microsoft.Office.Interop.Visio.Application.ActivePage](http://msdn.microsoft.com/library/office/ff765484.aspx) 属性和 [Microsoft.Office.Interop.Visio.Page.Drop](http://msdn.microsoft.com/library/office/ff765054.aspx) 方法的 VBA 参考文档。  
  
## <a name="adding-shapes-to-a-visio-document"></a>向 Visio 文档添加形状  
  
#### <a name="to-add-shapes-to-a-visio-document"></a>若要向 Visio 文档添加形状  
  
-   在文档处于活动状态的情况下，从 Documents.Masters 集合中检索主控形状并将形状放置在活动文档上。 可以使用索引或主控形状名称来检索主控形状。  
  
     下面的代码示例创建一个空白 Visio 文档，然后在“基本形状”  模具停靠的情况下打开它。 该代码随后检索多个形状并将它们放置在活动页面上。  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>请参阅  
 [Visio 解决方案](../vsto/visio-solutions.md)   
 [Visio 对象模型概述](../vsto/visio-object-model-overview.md)   
 [使用 Visio 形状](../vsto/working-with-visio-shapes.md)   
 [如何：以编程方式在 Visio 文档中复制和粘贴形状](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)  
  
  