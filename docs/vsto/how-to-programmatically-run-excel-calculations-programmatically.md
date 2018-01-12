---
title: "如何： 以编程方式进行 Excel 计算 |Microsoft 文档"
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
- ranges, running calculations
- calculations, running in Excel
- Excel [Office development in Visual Studio], running calculations programmatically
- workbooks, running calculations
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: d1b18b9de3c79385885c23fdbf0cac99a14c3e27
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-run-excel-calculations"></a>如何： 以编程方式进行 Excel 计算  
  你使用类似的过程运行计算<xref:Microsoft.Office.Tools.Excel.NamedRange>控件或本机 Excel 范围对象。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="running-calculations-in-a-namedrange-control"></a>NamedRange 控件中运行计算  
 下面的示例创建<xref:Microsoft.Office.Tools.Excel.NamedRange>A1 单元格上，然后计算单元格。 必须将此代码置于表类中，而不是在 `ThisWorkbook` 类中。  
  
#### <a name="to-run-calculations-in-a-namedrange-control"></a>NamedRange 控件中运行计算  
  
1.  创建命名的范围。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#75](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#75)]
     [!code-vb[Trin_VstcoreExcelAutomation#75](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#75)]  
  
2.  调用<xref:Microsoft.Office.Tools.Excel.NamedRange.Calculate%2A>方法指定的范围。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#76](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#76)]
     [!code-vb[Trin_VstcoreExcelAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#76)]  
  
## <a name="running-calculations-in-a-native-excel-range"></a>在本机 Excel 范围中运行计算  
  
#### <a name="to-run-calculations-in-a-native-excel-range"></a>若要运行本机 Excel 范围中的计算  
  
1.  创建命名的范围。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#30](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#30](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#30)]  
  
2.  调用<xref:Microsoft.Office.Interop.Excel.Range.Calculate%2A>方法指定的范围。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#31](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#31](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#31)]  
  
## <a name="see-also"></a>请参阅  
 [使用范围](../vsto/working-with-ranges.md)   
 [NamedRange 控件](../vsto/namedrange-control.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)  
  
  