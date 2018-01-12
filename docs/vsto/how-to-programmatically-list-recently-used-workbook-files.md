---
title: "如何： 以编程方式列出最近使用的工作簿文件 |Microsoft 文档"
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
- workbooks, listing recently used
- RecentFiles property
- Excel [Office development in Visual Studio], recently used files listing
- recent file list, Excel
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: e8a64f8a934e8cd7cdbbed11a87d15e795d19d0f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-list-recently-used-workbook-files"></a>如何：以编程方式列出最近使用的工作簿文件
  <xref:Microsoft.Office.Interop.Excel._Application.RecentFiles%2A>属性返回一个集合，其中包含的最近使用的文件的 Microsoft Office Excel 列表中显示的所有文件的名称。 列表的长度而异的用户已选定要保留的文件数。 你可以将范围中显示结果。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-list-recently-used-workbooks-in-a-range-object"></a>向最近使用列表范围对象中的工作簿  
  
1.  循环访问的最近使用的文件列表和相对于的单元中显示的名称<xref:Microsoft.Office.Interop.Excel.Range>对象。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>请参阅  
 [使用工作簿](../vsto/working-with-workbooks.md)   
 [NamedRange 控件](../vsto/namedrange-control.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)  
  
  