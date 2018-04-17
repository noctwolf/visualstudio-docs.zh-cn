---
title: 工作簿主机项 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel workbooks
- Workbook host items
- host items [Office development in Visual Studio], Workbook
- workbooks, Excel
- Workbook host items, events
- workbooks
- Excel [Office development in Visual Studio], workbooks
- workbooks, events
- events [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a5cf1281e084a5ffc51f06b35e3b1c68b2745c43
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="workbook-host-item"></a>工作簿宿主项
  <xref:Microsoft.Office.Tools.Excel.Workbook> 宿主项这种类型从 Excel 的主互操作程序集扩展 <xref:Microsoft.Office.Interop.Excel.Workbook> 类型。 <xref:Microsoft.Office.Tools.Excel.Workbook> 宿主项提供与 <xref:Microsoft.Office.Interop.Excel.Workbook> 对象完全相同的属性、方法和事件，但它还提供其他功能。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 在文档级项目中，有一个表示项目中的工作簿的默认 <xref:Microsoft.Office.Tools.Excel.Workbook> 宿主项。 在 VSTO 外接程序项目中，可以在运行时生成 <xref:Microsoft.Office.Tools.Excel.Workbook> 主机项。  
  
## <a name="understanding-the-workbook-host-item-in-document-level-projects"></a>了解文档级项目中的 Workbook 宿主项  
 若要访问项目中的工作簿，请使用 `ThisWorkbook` 类。 通过使用 `ThisWorkbook` 类，可以访问 <xref:Microsoft.Office.Tools.Excel.Workbook> 宿主项的成员，以执行自定义项中的基本任务，例如在打开或关闭工作簿时运行代码。 有关详细信息，请参阅 [Programming Document-Level Customizations](../vsto/programming-document-level-customizations.md)。  
  
 `ThisWorkbook` 类提供了一个位置，你可以在该位置开始编写项目中的代码。 因为该类提供与 Excel 主互操作程序集中的 <xref:Microsoft.Office.Interop.Excel.Workbook> 对象完全相同的属性、方法和事件，所以也可以使用 `ThisWorkbook` 访问 Excel 的对象模型。 有关详细信息，请参阅 [Excel Object Model Overview](../vsto/excel-object-model-overview.md)。  
  
 在“解决方案资源管理器”  中双击“ThisWorkbook”  项目项以显示工作簿设计器，并在“属性”  窗口中查看工作簿的属性和事件。  
  
### <a name="limitations-of-the-workbook-host-item-in-document-level-projects"></a>文档级项目中 Workbook 宿主项的限制  
 文档级项目只能包含一个 <xref:Microsoft.Office.Tools.Excel.Workbook> 宿主项（即 `ThisWorkbook` 类）。 不能在设计时将新的 <xref:Microsoft.Office.Tools.Excel.Workbook> 宿主项添加到项目，也不能在运行时从文档级自定义项创建新的 <xref:Microsoft.Office.Tools.Excel.Workbook> 宿主项。  
  
 如果在运行时创建新的 Excel 工作簿，则该工作簿为类型 <xref:Microsoft.Office.Interop.Excel.Workbook>。 因为它不是宿主项，所以它不能包含任何宿主控件或 Windows 窗体控件。 有关在运行时创建工作簿的详细信息，请参阅[如何： 以编程方式创建新工作簿](../vsto/how-to-programmatically-create-new-workbooks.md)。  
  
 <xref:Microsoft.Office.Tools.Excel.Workbook> 宿主项不充当宿主控件的容器。 因此，不能将任何可见控件添加到工作簿，但可以添加 <xref:System.Data.DataSet>等组件，以便这些组件可由所有工作表共享。 在文档级项目中，可用于工作簿的组件可在“工具箱”  的“组件”  选项卡、“数据”  选项卡和“所有 Windows 窗体” 选项卡中找到。  
  
> [!NOTE]  
>  Visual Studio 中的 Office 开发工具不支持共享工作簿。  
  
## <a name="understanding-workbook-host-items-in-vsto-add-in-projects"></a>了解 VSTO 外接程序项目中的 Workbook 宿主项  
 在 VSTO 外接程序项目中，可以在运行时为 Excel 中打开的任何工作簿生成 <xref:Microsoft.Office.Tools.Excel.Workbook> 宿主项。 若要生成<xref:Microsoft.Office.Tools.Excel.Workbook>宿主项，请使用 GetVstoObject 方法。 有关更多信息，请参见 [在运行时在 VSTO 外接程序中扩展 Word 文档和 Excel 工作簿](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)。  
  
## <a name="see-also"></a>请参阅  
 [Office 开发示例和演练](../vsto/office-development-samples-and-walkthroughs.md)   
 [在运行时扩展 Word 文档和 Excel 工作簿在 VSTO 外接程序](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [宿主项和宿主控件概述](../vsto/host-items-and-host-controls-overview.md)   
 [工作表主机项](../vsto/worksheet-host-item.md)   
 [使用扩展对象实现 Excel 自动化](../vsto/automating-excel-by-using-extended-objects.md)   
 [主机项和主机控件的编程限制](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  