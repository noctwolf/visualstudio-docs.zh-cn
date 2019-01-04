---
title: 如何：功能区上显示开发人员选项卡
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], tabs
- Developer tab [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c8346a1f23cc9aa02291aa994a0cea51b7810345
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53906795"
---
# <a name="how-to-show-the-developer-tab-on-the-ribbon"></a>如何：功能区上显示开发人员选项卡
  访问**开发人员**选项卡上的 Office 应用程序功能区中，您必须将其配置为显示该选项卡，因为它不会显示默认情况下。 例如，如果要向 Word 的文档级自定义项添加一个 <xref:Microsoft.Office.Tools.Word.GroupContentControl>，则必须显示该选项卡。  
  
> [!NOTE]  
>  本指南仅适用于 Office 2010 或更高版本的应用程序。 如果你想要在 2007 Microsoft Office System 中显示此选项卡，请参阅本主题的以下版本[如何：功能区上显示开发人员选项卡](https://web.archive.org/web/20140303033431/msdn.microsoft.com/library/bb608625(v=vs.90).aspx
)。  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
> [!NOTE]  
>  不具有访问权限**开发人员**选项卡。  
  
## <a name="to-show-the-developer-tab"></a>显示“开发工具”选项卡  
  
1.  启动本主题支持的任何 Office 应用程序。 请参阅**适用于：** 本主题前面的注意。  
  
2.  上**文件**选项卡上，选择**选项**按钮。  
  
     下图显示**文件**选项卡和**选项**Office 2010 中的按钮。  
  
     ![选择文件，Outlook 2010 中的选项](../vsto/media/vsto-office-file-tab.png "选择文件，Outlook 2010 中的选项")  
  
     下图显示**文件**Office 2013 中的选项卡。  
  
     ![Outlook 2013 中的文件选项卡](../vsto/media/vsto-office2013-filetab.png "Outlook 2013 中的文件选项卡")  
  
     下图显示**选项**Office 2013 中的按钮。  
  
     ![Outlook 2013 Preview 中的选项按钮](../vsto/media/vsto-office2013-optionsbutton.png "Outlook 2013 Preview 中的选项按钮")  
  
3.  在中_ApplicationName_**选项**对话框中，选择**自定义功能区**按钮。  
  
     下图显示**选项**对话框和**自定义功能区**Excel 2010 中的按钮。 此按钮的位置在本主题顶部附近“适用于”部分中列出的所有其他应用程序中是类似的。  
  
     ![自定义功能区按钮](../vsto/media/vsto-office2010-customizeribbonbutton.png "自定义功能区按钮")  
  
4.  在主选项卡的列表中选择**开发人员**复选框。  
  
     下图显示**开发人员**Word 2010 中的复选框和[!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]。 此复选框的位置在本主题顶部附近“适用于”部分中列出的所有其他应用程序中是类似的。  
  
     ![Word 选项对话框中的开发人员复选框](../vsto/media/vsto-office2010-developercheckbox.png "The Developer Word 选项对话框中的复选框")  
  
5.  选择**确定**按钮以关闭**选项**对话框。  
  
## <a name="see-also"></a>请参阅  
 [Office UI 自定义](../vsto/office-ui-customization.md)  
