---
title: 如何： 面向 Office 多语言用户界面
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
ms.openlocfilehash: 1b917479598b73f71a0f3092c874276a700717d6
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
ms.locfileid: "34262028"
---
# <a name="how-to-target-the-office-multilingual-user-interface"></a>如何： 面向 Office 多语言用户界面
  多语言用户界面 (MUI) 是使最终用户能够更改用户界面 (UI) 的语言的 Microsoft Office 功能。 例如，最终用户使用英语 UI 可以为西班牙语更改 UI 的语言。  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 如果你的应用程序将由使用的 Office 的多种语言的人员，你可以添加代码以自动更改 UI 字符串以匹配 Office 所使用的用户的计算机上 （如果该用户已安装了正确的资源） 的语言的语言。  
  
## <a name="to-check-the-current-office-ui-setting"></a>若要检查的当前 Office 用户界面设置  
  
1.  使用<xref:System.Threading.Thread.CurrentUICulture%2A>当前线程的属性。 将 UI 字符串以匹配的当前用户的计算机运行的 Office 版本所用的语言的语言设置。  
  
     [!code-vb[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#10)]
     [!code-csharp[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#10)]  
  
## <a name="see-also"></a>请参阅  
 [如何： 通过主互操作程序集的目标 Office 应用程序](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [在 Office 解决方案中的后期绑定](../vsto/late-binding-in-office-solutions.md)  
  
  