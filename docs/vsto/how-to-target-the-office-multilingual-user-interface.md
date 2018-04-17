---
title: 如何： 面向 Office 多语言用户界面 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- globalization [Office development in Visual Studio], user interface targeting
- MUI [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], localization
- Multilingual User Interface [Office development in Visual Studio]
- localization [Office development in Visual Studio], user interface targeting
- Office applications [Office development in Visual Studio], globalization
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 54b305311b686f527a79092280fbc33c3974247e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-target-the-office-multilingual-user-interface"></a>如何：面向 Office 多语言用户界面
  多语言用户界面 (MUI) 是使最终用户能够更改用户界面 (UI) 的语言的 Microsoft Office 功能。 例如，最终用户使用英语 UI 可以为西班牙语更改 UI 的语言。  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 如果你的应用程序将由使用 Office 的多个语言人员，你可以添加代码以自动更改 UI 字符串以匹配 Office 所使用的用户的计算机上 （如果该用户已安装了正确的资源） 的语言的语言。  
  
### <a name="to-check-the-current-office-ui-setting"></a>若要检查的当前 Office 用户界面设置  
  
1.  使用<xref:System.Threading.Thread.CurrentUICulture%2A>当前线程的属性。 将 UI 字符串以匹配正在使用的当前用户的计算机上运行的 Office 版本的语言的语言设置。  
  
     [!code-vb[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#10)]
     [!code-csharp[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#10)]  
  
## <a name="see-also"></a>请参阅  
 [如何：通过主互操作程序集面向 Office 应用程序](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Office 解决方案中的晚期绑定](../vsto/late-binding-in-office-solutions.md)  
  
  