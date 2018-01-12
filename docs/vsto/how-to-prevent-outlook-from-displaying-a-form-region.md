---
title: "如何： 防止 Outlook 显示窗体区域 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], canceling display
- canceling form region display
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: def4454f1031e5958dfc10e1a1fc77ccaed59067
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-prevent-outlook-from-displaying-a-form-region"></a>如何：防止 Outlook 显示窗体区域
  可能有不希望 Microsoft Office Outlook 显示特定项的窗体区域的情况。 例如，如果联系人项目不包含业务地址，你可以阻止在出现的地图中显示的业务位置的窗体区域。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
### <a name="to-prevent-outlook-from-displaying-a-form-region"></a>若要禁止 Outlook 显示窗体区域  
  
1.  打开你想要修改的窗体区域代码文件。  
  
2.  展开**窗体区域工厂**代码区域。  
  
3.  将代码添加到`FormRegionInitializing`设置的事件处理程序<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>属性<xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs>类到**true**。  
  
 在此示例中，如果联系人项目不包含地址、<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>属性设置为**true**，和窗体区域不会出现。  
  
## <a name="example"></a>示例  
 [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 [创建 Outlook 窗体区域](../vsto/creating-outlook-form-regions.md)   
 [演练： 设计 Outlook 窗体区域](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [如何： 向 Outlook 外接程序项目添加窗体区域](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [演练： 设计 Outlook 窗体区域](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [演练：导入在 Outlook 中设计的窗体区域](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  