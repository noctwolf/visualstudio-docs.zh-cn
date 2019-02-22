---
title: 如何：以编程方式检查文档中的拼写
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], checking spelling
- spelling checker, documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: cbb02ef8d1032a77cccd045401d9e3387f48a963
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56621092"
---
# <a name="how-to-programmatically-check-spelling-in-documents"></a>如何：以编程方式检查文档中的拼写
  若要检查文档中的拼写错误，请使用<xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A>方法。 此方法返回一个布尔值，该值指示所提供的参数是否拼写正确。

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="to-check-spelling-and-display-results-in-a-message-box"></a>若要检查拼写，并在消息框中显示结果

1.  调用<xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A>方法并将其传递要检查是否有拼写错误的文本范围。 若要使用此代码模板，请从项目中的 `ThisDocument` 或 `ThisAddIn` 类运行它。

     [!code-vb[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#113)]
     [!code-csharp[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#113)]

## <a name="see-also"></a>请参阅
- [如何：以编程方式定义和在文档中选择范围](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)
- [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)
