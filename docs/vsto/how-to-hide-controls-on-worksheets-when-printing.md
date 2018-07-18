---
title: 如何： 在打印时隐藏工作表上的控件
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- printing [Office development in Visual Studio], worksheets
- controls [Office development in Visual Studio], hiding while printing
- printing [Office development in Visual Studio], hiding controls
- worksheets, hiding controls when printing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e240f4b4be5ce4092705615f060f4e0ef0076e3a
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254467"
---
# <a name="how-to-hide-controls-on-worksheets-when-printing"></a>如何： 在打印时隐藏工作表上的控件
  如果打印包含 Windows 窗体控件的 Microsoft Office Excel 文档，控件将显示在打印工作表上。 打印工作表时，可以隐藏控件。  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  如果隐藏控件显示数据，如<xref:Microsoft.Office.Tools.Excel.Controls.TextBox>，控件中的数据将不可打印的工作表上可见。  
  
> [!NOTE]  
>  以下说明中的某些 Visual Studio 用户界面元素在计算机上出现的名称或位置可能会不同。 这些元素取决于你所使用的 Visual Studio 版本和你所使用的设置。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)。  
  
## <a name="to-hide-controls-when-a-worksheet-is-printed"></a>若要隐藏工作表时的控件打印  
  
1.  创建或在 Visual Studio 中打开 Excel 项目并确认**Sheet1**在设计器中可见。 有关创建项目的信息，请参阅[如何： 在 Visual Studio 中的创建 Office 项目](../vsto/how-to-create-office-projects-in-visual-studio.md)。  
  
2.  从**公共控件**选项卡**工具箱**，将<xref:Microsoft.Office.Tools.Excel.Controls.Button>控制到单元格上`Sheet1`。  
  
3.  在中**属性**窗口中，将<xref:Microsoft.Office.Tools.Excel.Controls.Button.PrintObject%2A>属性设置为**False**。  
  
## <a name="see-also"></a>请参阅  
 [Office 文档上的控件](../vsto/controls-on-office-documents.md)   
 [Windows 窗体控件在 Office 文档概述](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [如何： 向 Office 文档添加 Windows 窗体控件](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [如何： 调整工作表单元格中的控件的大小](../vsto/how-to-resize-controls-within-worksheet-cells.md)  
  
  