---
title: "如何： 以编程方式保存 Outlook 电子邮件项的附件 |Microsoft 文档"
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
- Outlook [Office development in Visual Studio], attachments
- e-mail [Office development in Visual Studio], attachments
- saving e-mail attachments
- mail items [Office development in Visual Studio], attachments
- attachments [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: f87b05b45fafab3ad28a6da6a98391b8d121be7e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-save-attachments-from-outlook-e-mail-items"></a>如何：以编程方式保存 Outlook 电子邮件项的附件
  此示例会在收件箱接收到电子邮件时将邮件中的附件保存到指定的文件夹中。  
  
> [!IMPORTANT]  
>  此示例正常仅当你添加名为的文件夹**TestFileSave**在 C 目录的根目录。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>示例  
 [!code-csharp[Trin_OL_SaveAttachments#1](../vsto/codesnippet/CSharp/Trin_OL_SaveAttachments/thisaddin.cs#1)]  
  
## <a name="see-also"></a>请参阅  
 [使用邮件项](../vsto/working-with-mail-items.md)   
 [如何： 以编程方式检索按名称的文件夹](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [如何： 以编程方式在收到电子邮件后执行操作](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)   
 [如何：以编程方式在特定文件夹中进行搜索](../vsto/how-to-programmatically-search-within-a-specific-folder.md)  
  
  