---
title: 如何： 以编程方式打开文本文件作为工作簿
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b7bc7caa5dbceb727394b8543b7659cc43e64a36
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257642"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>如何： 以编程方式打开文本文件作为工作簿
  为工作簿，可以打开一个文本文件。 您必须传递你想要打开的文本文件的名称。 可以指定几个可选参数，例如，要从哪一行开始分析以及文件中的数据的列格式。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>示例  
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]  
  
## <a name="compile-the-code"></a>编译代码  
 此示例需要以下组件：  
  
-   名为的逗号分隔的文本文件`Test.txt`，其中包含至少三行文本。  
  
-   该文本文件`Test.txt`要存储在驱动器 c。  
  
## <a name="see-also"></a>请参阅  
 [使用工作簿](../vsto/working-with-workbooks.md)   
 [如何： 以编程方式打开工作簿](../vsto/how-to-programmatically-open-workbooks.md)   
 [如何： 以编程方式创建新的工作簿](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [如何： 以编程方式保存工作簿](../vsto/how-to-programmatically-save-workbooks.md)   
 [如何： 以编程方式关闭工作簿](../vsto/how-to-programmatically-close-workbooks.md)   
 [Office 解决方案中的可选参数](../vsto/optional-parameters-in-office-solutions.md)  
  
  