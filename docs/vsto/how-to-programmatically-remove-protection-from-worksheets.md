---
title: "如何： 以编程方式取消工作表保护 |Microsoft 文档"
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
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1b4564baab3cf2daa6e8859a66dbc6e9e06ffdef
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-remove-protection-from-worksheets"></a>如何：以编程方式取消工作表保护
  可以编程方式取消 Microsoft Office Excel 工作表保护。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 以下示例使用变量 `getPasswordFromUser`，该变量包含获取自用户的密码。  
  
### <a name="to-unprotect-a-worksheet-in-a-document-level-customization"></a>若要在文档级自定义中取消工作表的保护  
  
1.  调用工作表的 <xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A> 方法并传入密码（如果需要）。 此示例假定你正在使用名为 `Sheet1`的工作表。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#28)]  
  
### <a name="to-unprotect-a-worksheet-in-an-vsto-add-in"></a>在 VSTO 外接程序中取消工作表保护  
  
1.  调用活动工作表的 <xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A> 方法并传入密码（如果需要）。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#18)]  
  
## <a name="see-also"></a>请参阅  
 [使用工作表](../vsto/working-with-worksheets.md)   
 [如何： 以编程方式保护工作表](../vsto/how-to-programmatically-protect-worksheets.md)   
 [如何： 以编程方式保护工作簿](../vsto/how-to-programmatically-protect-workbooks.md)   
 [如何： 以编程方式隐藏工作表](../vsto/how-to-programmatically-hide-worksheets.md)   
 [对 Office 项目中对象的全局访问](../vsto/global-access-to-objects-in-office-projects.md)  
  
  