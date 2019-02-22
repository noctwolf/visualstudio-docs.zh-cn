---
title: 如何：以编程方式搜索特定联系人
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- contacts [Office development in Visual Studio], searching
- searching contacts
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: feff583d28bf53f4bffc9b425d52902688b80a4b
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607156"
---
# <a name="how-to-programmatically-search-for-a-specific-contact"></a>如何：以编程方式搜索特定联系人
  此示例按姓氏和名称在 Outlook 联系人文件夹中搜索特定联系人。 该示例假定联系人文件夹中存在名为 **John Evans** 的联系人。

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>示例
 [!code-csharp[Trin_Outlook_RL_SearchForContact#1](../vsto/codesnippet/CSharp/trin_outlook_rl_searchforcontact/thisaddin.cs#1)]
 [!code-vb[Trin_Outlook_RL_SearchForContact#1](../vsto/codesnippet/VisualBasic/trin_outlook_rl_searchforcontact/thisaddin.vb#1)]

## <a name="see-also"></a>请参阅
- [使用联系人项](../vsto/working-with-contact-items.md)
- [VSTO 外接程序编程入门](../vsto/getting-started-programming-vsto-add-ins.md)
