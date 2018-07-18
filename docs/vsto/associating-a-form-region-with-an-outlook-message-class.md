---
title: 将窗体区域与 Outlook 邮件类关联
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.InvalidMessageClassName
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FormRegionMessageClassAttribute
- form regions [Office development in Visual Studio], message classes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d6f48be189b7d7a35f713c224553dc9ad7c8a5c3
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
ms.locfileid: "34268225"
---
# <a name="associate-a-form-region-with-an-outlook-message-class"></a>将窗体区域与 Outlook 邮件类关联
  你可以指定将显示的窗体区域的 Microsoft Office Outlook 项通过将窗体区域与每个项的邮件类关联。 例如，如果你想要将窗体区域附加到邮件项底部，则可以将窗体区域与`IPM.Note`message 类。  
  
 若要将与消息类关联的窗体区域，指定在的 message 类名称**新建 Outlook 窗体区域**向导或将特性应用于窗体区域工厂类。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="understand-outlook-message-classes"></a>了解 Outlook 邮件类  
 Outlook 邮件类标识的 Outlook 项的类型。 下表列出这些八个的标准类型的项和其 message 类名称。  
  
|Outlook 项类型|Message 类名称|  
|-----------------------|------------------------|  
|AppointmentItem|`IPM.Appointment`|  
|ContactItem|`IPM.Contact`|  
|DistListItem|`IPM.DistList`|  
|JournalItem|`IPM.Activity`|  
|MailItem|`IPM.Note`|  
|PostItem|`IPM.Post` 或 `IPM.Post.RSS`|  
|TaskItem|`IPM.Task`|  
  
 你还可以指定自定义邮件类的名称。 自定义邮件类标识你在 Outlook 中定义的自定义窗体。  
  
> [!NOTE]  
>  对于替换和全部替换窗体区域，你可以指定新的自定义 message 类名称。 不需要使用现有的自定义窗体的 message 类名。 自定义邮件类的名称必须是唯一的。 请确保名称唯一的一种方法是使用类似于以下的命名约定： \<*标准邮件类名称*>。\<*公司*>。\<*MessageClassName*> (例如： `IPM.Note.Contoso.MyMessageClass`)。  
  
## <a name="associate-a-form-region-with-an-outlook-message-class"></a>将窗体区域与 Outlook 邮件类关联  
 有两种方法可以将窗体区域与消息类相关联：  
  
-   使用**新建 Outlook 窗体区域**向导。  
  
-   将类属性的应用。  
  
### <a name="use-the-new-outlook-form-region-wizard"></a>使用新建 Outlook 窗体区域向导  
 最后一页上**新建 Outlook 窗体区域**向导，你可以选择标准消息类，然后键入你想要与窗体区域关联的自定义邮件类的名称。  
  
 标准消息类不可用，如果窗体区域旨在替换整个窗体或窗体的默认页。 你可以指定标准消息仅对用于将一个新页面添加到窗体或追加到窗体的底部的窗体的类名称。 有关详细信息，请参阅[如何： 向 Outlook 外接程序项目添加窗体区域](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)。  
  
 若要包含一个或多个自定义邮件类，请键入其名称中的**哪些自定义邮件类将显示此窗体区域？** 框。  
  
 您键入的名称必须符合以下准则：  
  
-   使用完全限定的 message 类名称 (例如:"IPM。Note.Contoso")。  
  
-   使用分号分隔多个邮件类名称。  
  
-   不包括标准 Outlook message 类，如"IPM。请注意"或者"IPM。联系"。 只能包含自定义邮件类，如"IPM。Note.Contoso"。  
  
-   不指定基的 message 类本身 (例如:"IPM")。  
  
-   不能超过 256 个字符为每个消息类名。  
  
 **新建 Outlook 窗体区域**单击时，向导将验证你输入的格式**完成**。  
  
> [!NOTE]  
>  **新建 Outlook 窗体区域**向导不验证你提供的邮件类名称是否正确或有效。  
  
 在完成向导，**新建 Outlook 窗体区域**向导将特性应用于包含指定的消息类名称的窗体区域类。 你还可以手动应用这些属性。  
  
### <a name="apply-class-attributes"></a>应用类特性  
 在完成后，你可以使用 Outlook 邮件类关联的窗体区域**新建 Outlook 窗体区域**向导。 若要执行此操作，请将特性应用于窗体区域工厂类。  
  
 下面的示例显示了两个<xref:Microsoft.Office.Tools.Outlook.FormRegionMessageClassAttribute>已应用于名为的窗体区域工厂类的属性`myFormRegion`。 第一个属性将窗体区域与邮件窗体的标准消息类相关联。 第二个特性将窗体区域与名为的自定义消息类相关联`IPM.Task.Contoso`。  
  
 [!code-vb[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Attributes/FormRegion1.vb#1)]
 [!code-csharp[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Attributes/FormRegion1.cs#1)]  
  
 属性必须符合以下准则：  
  
-   对于自定义邮件类，使用完全限定的 message 类名称 (例如:"IPM。Note.Contoso")。  
  
-   不指定基的 message 类本身 (例如:"IPM")。  
  
-   不能超过 256 个字符为每个消息类名。  
  
-   如果窗体区域替换整个窗体或窗体的默认页，则不包括标准消息类的名称。 你可以指定标准消息仅对用于将一个新页面添加到窗体或追加到窗体的底部的窗体的类名称。 有关详细信息，请参阅[如何： 向 Outlook 外接程序项目添加窗体区域](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)。  
  
 生成项目时，visual Studio 会验证消息类名称的格式。  
  
> [!NOTE]  
>  Visual Studio 不验证你提供的邮件类名称正确或有效。  
  
## <a name="see-also"></a>请参阅  
 [访问窗体区域在运行时](../vsto/accessing-a-form-region-at-run-time.md)   
 [创建 Outlook 窗体区域](../vsto/creating-outlook-form-regions.md)   
 [演练： 设计 Outlook 窗体区域](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [准则创建 Outlook 窗体区域](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [窗体 name 和 message 类概述](http://msdn.microsoft.com/library/office/ff867629.aspx)   
 [Outlook 窗体和项如何协同工作](http://msdn.microsoft.com/library/office/ff869706.aspx)  
  
  