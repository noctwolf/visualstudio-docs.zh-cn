---
title: 如何：以编程方式确定当前的 Outlook 项
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], current
- e-mail [Office development in Visual Studio], current item
- SelectionChange event
- Outlook [Office development in Visual Studio], current item
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 3608f516eb9206bc5b4c232c227d3e49c2414be7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56599748"
---
# <a name="how-to-programmatically-determine-the-current-outlook-item"></a>如何：以编程方式确定当前的 Outlook 项
  此示例使用`Explorer.SelectionChange`事件，以显示当前文件夹并选定项的一些信息的名称。 然后，代码将显示选定的项。

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>示例
 [!code-vb[Trin_OL_CurrentItem#1](../vsto/codesnippet/VisualBasic/Trin_OL_CurrentItem/thisaddin.vb#1)]
 [!code-csharp[Trin_OL_CurrentItem#1](../vsto/codesnippet/CSharp/Trin_OL_CurrentItem/thisaddin.cs#1)]

## <a name="compile-the-code"></a>编译代码
 此示例需要：

-   约会、 联系人和 Microsoft Office Outlook 中的电子邮件项。

## <a name="see-also"></a>请参阅
- [Outlook 对象模型概述](../vsto/outlook-object-model-overview.md)
- [如何：以编程方式按名称检索文件夹](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)
- [如何：以编程方式搜索特定联系人](../vsto/how-to-programmatically-search-for-a-specific-contact.md)
