---
title: "如何： 以编程方式打开工作簿 |Microsoft 文档"
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
- workbooks, opening
- Excel [Office development in Visual Studio], opening workbooks
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 11fe801cf80c15953056f4f6fdd50c5c4fadd3c9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-open-workbooks"></a>如何：以编程方式打开工作簿
  <xref:Microsoft.Office.Interop.Excel.Workbooks>在 Microsoft Office Excel 中的集合有可能用于所有打开的工作簿并打开工作簿。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-open-an-existing-workbook"></a>若要打开现有工作簿  
  
1.  使用<xref:Microsoft.Office.Interop.Excel.Workbooks.Open%2A>方法<xref:Microsoft.Office.Interop.Excel.Workbooks>集合，在路径中将传递给该工作簿。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#2)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此代码示例要求满足以下条件：  
  
-   名为工作簿`YourWorkbook.xls`必须存在于一个名为目录`Test`驱动器 C 上  
  
## <a name="see-also"></a>请参阅  
 [使用工作簿](../vsto/working-with-workbooks.md)   
 [如何： 以编程方式打开文本文件作为工作簿](../vsto/how-to-programmatically-open-text-files-as-workbooks.md)   
 [如何： 以编程方式创建新的工作簿](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [如何： 以编程方式保存工作簿](../vsto/how-to-programmatically-save-workbooks.md)   
 [如何： 以编程方式关闭工作簿](../vsto/how-to-programmatically-close-workbooks.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)   
 [主机项和主机控件概述](../vsto/host-items-and-host-controls-overview.md)  
  
  