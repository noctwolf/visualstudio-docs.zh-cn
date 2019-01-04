---
title: 如何：以编程方式保存 Outlook 电子邮件项的附件
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook [Office development in Visual Studio], attachments
- e-mail [Office development in Visual Studio], attachments
- saving e-mail attachments
- mail items [Office development in Visual Studio], attachments
- attachments [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ec543a23a68965c0fa629d7318f40e840fb81152
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53911229"
---
# <a name="how-to-programmatically-save-attachments-from-outlook-email-items"></a>如何：以编程方式保存 Outlook 电子邮件项的附件
  此示例会在收件箱接收到电子邮件时将邮件中的附件保存到指定的文件夹中。  
  
> [!IMPORTANT]  
>  此示例仅适用于添加名为的文件夹**TestFileSave** C 目录的根目录。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>示例  
 [!code-csharp[Trin_OL_SaveAttachments#1](../vsto/codesnippet/CSharp/Trin_OL_SaveAttachments/thisaddin.cs#1)]  
  
## <a name="see-also"></a>请参阅  
 [使用邮件项](../vsto/working-with-mail-items.md)   
 [如何：以编程方式按名称检索文件夹](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [如何：以编程方式执行操作时收到一封电子邮件](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)   
 [如何：以编程方式在特定文件夹内的搜索](../vsto/how-to-programmatically-search-within-a-specific-folder.md)  
