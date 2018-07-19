---
title: 如何： 以编程方式检查文档中的拼写
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], checking spelling
- spelling checker, documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e916b16caaaa3944fcdf522ffd320198d9972b52
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256713"
---
# <a name="how-to-programmatically-check-spelling-in-documents"></a>如何： 以编程方式检查文档中的拼写
  若要检查文档中的拼写错误，请使用<xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A>方法。 此方法返回一个布尔值，该值指示所提供的参数是否拼写正确。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-check-spelling-and-display-results-in-a-message-box"></a>若要检查拼写，并在消息框中显示结果  
  
1.  调用<xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A>方法并将其传递要检查是否有拼写错误的文本范围。 若要使用此代码模板，请从项目中的 `ThisDocument` 或 `ThisAddIn` 类运行它。  
  
     [!code-vb[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#113)]
     [!code-csharp[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#113)]  
  
## <a name="see-also"></a>请参阅  
 [如何： 以编程方式定义和在文档中选择范围](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)  
  
  