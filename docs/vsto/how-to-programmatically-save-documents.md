---
title: 如何：以编程方式保存文档
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], saving
- Word [Office development in Visual Studio], saving documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 0e455df89a3dfece2c5d4c8cd36a26af816f720a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63419458"
---
# <a name="how-to-programmatically-save-documents"></a>如何：以编程方式保存文档
  有几种方法来保存 Microsoft Office Word 文档。 您可以将文档保存而无需更改文档的名称或可以使用新名称保存文档。

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="save-a-document-without-changing-the-name"></a>保存文档，而无需更改名称

### <a name="to-save-the-document-associated-with-a-document-level-customization"></a>若要保存与文档级自定义关联的文档

1. 调用 <xref:Microsoft.Office.Tools.Word.Document.Save%2A> 类的 <xref:Microsoft.Office.Tools.Word.Document> 方法。 若要使用此代码示例，请从项目中的 `ThisDocument` 类运行它。

     [!code-vb[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#7)]
     [!code-csharp[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#7)]

### <a name="to-save-the-active-document"></a>若要保存活动文档

1. 调用<xref:Microsoft.Office.Interop.Word._Document.Save%2A>活动文档的方法。 若要使用此代码模板，请从项目中的 `ThisDocument` 或 `ThisAddIn` 类运行它。

    [!code-vb[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#8)]
    [!code-csharp[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#8)]

   如果不确定要用于保存的文档是否是活动文档，可以按其名称来引用它。

### <a name="to-save-a-document-specified-by-name"></a>若要保存由名称指定的文档

1. 使用文档名称的参数作为<xref:Microsoft.Office.Interop.Word.Documents>集合。 若要使用此代码模板，请从项目中的 `ThisDocument` 或 `ThisAddIn` 类运行它。

     [!code-vb[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#9)]
     [!code-csharp[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#9)]

## <a name="save-a-document-with-a-new-name"></a>使用新名称保存文档
 SaveAs 方法用于使用新名称保存文档。 可以使用这种方法<xref:Microsoft.Office.Tools.Word.Document>宿主项在文档级 Word 项目中，或本机的<xref:Microsoft.Office.Interop.Word.Document>任何 Word 项目中的对象。 此方法要求指定新文件名，但其他参数是可选的。

> [!NOTE]
> 如果显示**另存为**对话框中的内部<xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave>事件处理程序`ThisDocument`并设置*取消*参数**false**，应用程序可能意外退出。 如果您设置*取消*参数**true**，将显示错误消息，指示已禁用了自动保存。

### <a name="to-save-the-document-associated-with-a-document-level-customization-with-a-new-name"></a>若要保存与具有新名称的文档级自定义项关联的文档

1. 调用<xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A>方法的`ThisDocument`类在项目中，使用完全限定的路径和文件名。 如果该文件夹中已存在具有该名称的文件，则以无提示方式覆盖它。 若要使用此代码示例，请从 `ThisDocument` 类中运行它。

    > [!NOTE]
    > <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A>方法将引发异常，如果目标目录不存在或保存文件的其他问题。 它是使用一个好办法**try...catch**阻止围绕<xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A>方法或在调用方法。

     [!code-vb[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#10)]

### <a name="to-save-a-native-document-with-a-new-name"></a>若要使用新名称保存本机文档

1. 调用<xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A>方法的<xref:Microsoft.Office.Interop.Word.Document>要保存，请使用完全限定的路径和文件名。 如果该文件夹中已存在具有该名称的文件，则以无提示方式覆盖它。

     下面的代码示例将使用新名称保存活动文档。 若要使用此代码模板，请从项目中的 `ThisDocument` 或 `ThisAddIn` 类运行它。

    > [!NOTE]
    > <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A>方法将引发异常，如果目标目录不存在或保存文件的其他问题。 它是使用一个好办法**try...catch**阻止围绕<xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A>方法或在调用方法。

     [!code-vb[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#10)]

## <a name="compile-the-code"></a>编译代码
 此代码示例要求满足以下条件：

- 若要按名称保存文档，文档名为*NewDocument.doc*必须存在于一个名为目录*测试*在驱动器 c。

- 若要使用新名称保存文档，目录的名称*测试*必须位于驱动器 c。

## <a name="see-also"></a>请参阅
- [如何：以编程方式关闭文档](../vsto/how-to-programmatically-close-documents.md)
- [如何：以编程方式打开现有文档](../vsto/how-to-programmatically-open-existing-documents.md)
- [文档主机项](../vsto/document-host-item.md)
- [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)
