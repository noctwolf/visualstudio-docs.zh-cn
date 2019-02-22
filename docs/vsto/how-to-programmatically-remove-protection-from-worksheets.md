---
title: 如何：以编程方式取消工作表保护
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bd071a10ab456014190df4f84d6a0bff13c859b8
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604837"
---
# <a name="how-to-programmatically-remove-protection-from-worksheets"></a>如何：以编程方式取消工作表保护
  可以编程方式取消 Microsoft Office Excel 工作表保护。

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 以下示例使用变量 `getPasswordFromUser`，该变量包含获取自用户的密码。

## <a name="to-unprotect-a-worksheet-in-a-document-level-customization"></a>若要在文档级自定义中取消工作表的保护

1.  调用<xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A>工作表并传入密码，如有必要的方法。 此示例假定你正在使用名为 `Sheet1`的工作表。

     [!code-csharp[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#28)]

## <a name="to-unprotect-a-worksheet-in-a-vsto-add-in"></a>若要取消保护 VSTO 外接程序中的工作表

1.  调用<xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A>活动工作表并传入密码，如有必要的方法。

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#18)]

## <a name="see-also"></a>请参阅
- [使用工作表](../vsto/working-with-worksheets.md)
- [如何：以编程方式保护工作表](../vsto/how-to-programmatically-protect-worksheets.md)
- [如何：以编程方式保护工作簿](../vsto/how-to-programmatically-protect-workbooks.md)
- [如何：以编程方式隐藏工作表](../vsto/how-to-programmatically-hide-worksheets.md)
- [对 Office 项目中的对象的全局访问](../vsto/global-access-to-objects-in-office-projects.md)
