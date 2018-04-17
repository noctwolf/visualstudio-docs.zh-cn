---
title: 如何： 以编程方式在工作表中的行分组 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, creating groups
- groups, creating in worksheets
- ranges, creating groups
- worksheets, clearing groups
- groups
- groups [Office development in Visual Studio], clearing in worksheets
- worksheets, ungrouping rows and columns
- rows [Office development in Visual Studio], ungrouping
- columns [Office development in Visual Studio], ungrouping
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 894e3971c257a6461aa975a9d6bb1cf933234440
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-group-rows-in-a-worksheet"></a>如何：以编程方式将工作表中的行分组
  你可以在一个或多个整个行进行分组。 若要在工作表中创建组，请使用<xref:Microsoft.Office.Tools.Excel.NamedRange>控件或本机 Excel 范围对象。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>使用 NamedRange 控件  
 如果你添加<xref:Microsoft.Office.Tools.Excel.NamedRange>控件到文档级项目中在设计时，你可以使用控件以编程方式创建一个组。 下面的示例假定有三个<xref:Microsoft.Office.Tools.Excel.NamedRange>所在的工作表上的控件： `data2001`， `data2002`，和`dataAll`。 每个命名的范围引用工作表中的整个一行。  
  
#### <a name="to-create-a-group-of-namedrange-controls-on-a-worksheet"></a>若要创建一组工作表上的 NamedRange 控件  
  
1.  通过调用组三个命名的范围<xref:Microsoft.Office.Tools.Excel.NamedRange.Group%2A>的每个范围的方法。 必须将此代码置于表类中，而不是在 `ThisWorkbook` 类中。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#32](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#32)]
     [!code-vb[Trin_VstcoreExcelAutomation#32](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#32)]  
  
    > [!NOTE]  
    >  若要对行进行取消分组，调用<xref:Microsoft.Office.Tools.Excel.NamedRange.Ungroup%2A>方法。  
  
## <a name="using-native-excel-ranges"></a>使用本机 Excel 范围  
 该代码假定你有三个名为的 Excel 范围`data2001`， `data2002`，和`dataAll`工作表上。  
  
#### <a name="to-create-a-group-of-excel-ranges-in-a-worksheet"></a>若要在工作表中创建的 Excel 范围组  
  
1.  通过调用组三个命名的范围<xref:Microsoft.Office.Interop.Excel.Range.Group%2A>的每个范围的方法。 下面的示例假定有三个<xref:Microsoft.Office.Interop.Excel.Range>控件名为`data2001`， `data2002`，和`dataAll`在所在的工作表上。 每个命名的范围引用工作表中的整个一行。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#33](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#33)]
     [!code-vb[Trin_VstcoreExcelAutomation#33](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#33)]  
  
    > [!NOTE]  
    >  若要对行进行取消分组，调用<xref:Microsoft.Office.Interop.Excel.Range.Ungroup%2A>方法。  
  
## <a name="see-also"></a>请参阅  
 [使用工作表](../vsto/working-with-worksheets.md)   
 [NamedRange 控件](../vsto/namedrange-control.md)   
 [如何： 向工作表添加 NamedRange 控件](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)  
  
  