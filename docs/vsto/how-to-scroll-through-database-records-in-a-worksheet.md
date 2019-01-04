---
title: 如何：滚动工作表中的数据库记录
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
- worksheets [Office development in Visual Studio], scrolling records
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1459ee941a8cb88d102e14ccfc7f128796c4c333
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53897465"
---
# <a name="how-to-scroll-through-database-records-in-a-worksheet"></a>如何：滚动工作表中的数据库记录
  以下过程说明如何使用设计器来显示单个字段从数据库表中的 Microsoft Office Excel 工作表，使最终用户可以滚动浏览所有记录的控件。  
  
 仅在文档级项目中，可以使用设计器。 但是，还可以添加控件并将其绑定到以编程方式在运行时数据。 有关详细信息，请参见[演练：VSTO 外接程序项目中的简单数据绑定](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md)。  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
## <a name="to-scroll-through-database-records-in-a-worksheet"></a>可滚动显示各个工作表中的数据库记录  
  
1.  在 Visual Studio 中打开一个 Excel 应用程序项目。  
  
2.  打开**数据源**窗口并从数据库创建数据源。 有关详细信息，请参阅[添加新连接](../data-tools/add-new-connections.md)。  
  
3.  展开包含你想要显示的数据的表并选择特定列。  
  
4.  打开列表控件，然后选择**NamedRange**。  
  
5.  拖动<xref:Microsoft.Office.Tools.Excel.NamedRange>控件拖动到想要显示的数据的单元格。  
  
6.  从**Windows 窗体**选项卡**工具箱**，将添加<xref:System.Windows.Forms.BindingNavigator>控制到工作表，并设置你想要使用的控件。 有关详细信息，请参阅[BindingNavigator 控件概述&#40;Windows 窗体&#41;](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms)。  
  
## <a name="see-also"></a>请参阅  
 [将数据绑定到 Office 解决方案中的控件](../vsto/binding-data-to-controls-in-office-solutions.md)  
