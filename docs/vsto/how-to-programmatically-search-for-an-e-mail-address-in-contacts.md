---
title: "如何： 以编程方式在联系人中电子邮件地址搜索 |Microsoft 文档"
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
- e-mail [Office development in Visual Studio], searching
- contacts [Office development in Visual Studio], searching
- searching contacts
ms.assetid: e973a407-8b94-45c7-acdf-fe330115fb33
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 57c0cac0dd2b22b38284caec0a2bfb40d6e5b101
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-search-for-an-e-mail-address-in-contacts"></a>如何：以编程方式在联系人中搜索电子邮件地址
  以下示例将在联系人文件夹搜索电子邮件地址中具有域名 **example.com** 的联系人。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>示例  
 [!code-csharp[Trin_OL_SearchEmail#1](../vsto/codesnippet/CSharp/Trin_OL_SearchEmail/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   电子邮件地址中具有域名 **example.com** （例如， `somebody@example.com`且具有的名字和姓氏的联系人。  
  
## <a name="see-also"></a>请参阅  
 [使用联系人项](../vsto/working-with-contact-items.md)   
 [如何： 以编程方式发送电子邮件](../vsto/how-to-programmatically-send-e-mail-programmatically.md)   
 [如何： 以编程方式访问 Outlook 联系人](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [如何：以编程方式将条目添加到 Outlook 联系人](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)  
  
  