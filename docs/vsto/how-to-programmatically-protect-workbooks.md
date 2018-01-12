---
title: "如何： 以编程方式保护工作簿 |Microsoft 文档"
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
- workbooks, passwords
- documents [Office development in Visual Studio], document protection
- workbooks, unprotecting
- document protection, removing from workbooks
- document protection, adding to workbooks
- workbooks, protecting
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1799366258786bafb3b24b5580ccf29be1d59927
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-protect-workbooks"></a>如何：以编程方式保护工作簿
  你可以保护 Microsoft Office Excel 工作簿，以便用户无法添加或删除工作表，并且还以编程方式取消保护工作簿。 （可选） 可以指定密码，指示是否希望保护 （以便用户无法移动表），该结构并且指示您要保护的工作簿的 windows。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 保护工作簿不阻止用户编辑单元格。 若要保护的数据，您必须保护工作表。 有关详细信息，请参阅[如何： 以编程方式保护工作表](../vsto/how-to-programmatically-protect-worksheets.md)。  
  
 下面的代码示例使用变量来存放从用户获得的密码。  
  
## <a name="protecting-a-workbook-that-is-part-of-a-document-level-customization"></a>保护属于文档级自定义项的工作簿  
  
#### <a name="to-protect-a-workbook"></a>若要保护工作簿  
  
1.  调用<xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A>工作簿的方法并包含一个密码。 若要使用下面的代码示例，运行`ThisWorkbook`类，不在表类中。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#10)]
     [!code-vb[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#10)]  
  
#### <a name="to-unprotect-a-workbook"></a>若要取消保护工作簿  
  
1.  调用<xref:Microsoft.Office.Tools.Excel.Workbook.Unprotect%2A>传递密码，如果它是必需的方法。 若要使用下面的代码示例，运行`ThisWorkbook`类，不在表类中。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#11)]  
  
## <a name="protecting-a-workbook-by-using-an-application-level-add-in"></a>使用应用程序级外接程序保护工作簿  
  
#### <a name="to-protect-a-workbook"></a>若要保护工作簿  
  
1.  调用<xref:Microsoft.Office.Interop.Excel._Workbook.Protect%2A>工作簿的方法并包含一个密码。 此代码示例使用活动的工作簿。 若要使用此示例，请从项目的 `ThisAddIn` 类中运行代码。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#6)]  
  
#### <a name="to-unprotect-a-workbook"></a>若要取消保护工作簿  
  
1.  调用<xref:Microsoft.Office.Interop.Excel._Workbook.Unprotect%2A>的活动工作簿，如果需要传递密码的方法。 若要使用此示例，请从项目的 `ThisAddIn` 类中运行代码。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>请参阅  
 [使用工作簿](../vsto/working-with-workbooks.md)   
 [如何： 以编程方式保护工作表](../vsto/how-to-programmatically-protect-worksheets.md)   
 [如何： 以编程方式隐藏工作表](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)  
  
  