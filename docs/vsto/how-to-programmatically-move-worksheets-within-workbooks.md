---
title: 如何： 以编程方式移动工作簿内的工作表
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, moving
- workbooks, moving worksheets in
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5075008e3b6b2b6f9ae087c0cfe962f2a1191f52
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "35670290"
---
# <a name="how-to-programmatically-move-worksheets-within-workbooks"></a>如何： 以编程方式移动工作簿内的工作表
  可以通过编程方式更改工作簿中工作表相对于其他工作表的位置。 如果不为移动的工作表指定位置，Excel 将创建新的工作簿来容纳它。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="to-move-a-worksheet-in-a-document-level-customization"></a>在文档级自定义项中移动工作表  
  
1.  将工作簿中的工作表的总数分配给一个变量，然后移动第一个工作表，使其成为最后一个工作表。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#24)]  
  
## <a name="to-move-a-worksheet-in-a-vsto-add-in"></a>VSTO 外接程序中移动工作表  
  
1.  将工作簿中的工作表的总数分配给一个变量，然后移动第一个工作表，使其成为最后一个工作表。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#16)]  
  
## <a name="see-also"></a>请参阅  
 [使用工作表](../vsto/working-with-worksheets.md)   
 [如何： 以编程方式隐藏工作表](../vsto/how-to-programmatically-hide-worksheets.md)   
 [如何： 以编程方式从工作簿中删除工作表](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [如何： 以编程方式保护工作表](../vsto/how-to-programmatically-protect-worksheets.md)   
 [对 Office 项目中的对象的全局访问](../vsto/global-access-to-objects-in-office-projects.md)  
  
  