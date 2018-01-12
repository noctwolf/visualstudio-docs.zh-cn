---
title: "如何： 以编程方式在特定文件夹中搜索 |Microsoft 文档"
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
helpviewer_keywords: Outlook folders [Office development in Visual Studio], searching
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 71b9da77857bb82a27f6bd6ae057a1df1fca8a1d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-search-within-a-specific-folder"></a>如何：以编程方式在特定文件夹中搜索
  此代码示例使用`Find`和`FindNext`方法以在电子邮件中的主题字段中搜索文本**收件箱**。 此方法使用字符串筛选器来检查程序字母 T 的起始号作为`Subject`文本。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>示例  
 [!code-csharp[Trin_OL_SearchFolder#1](../vsto/codesnippet/CSharp/Trin_OL_SearchFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>请参阅  
 [使用文件夹](../vsto/working-with-folders.md)   
 [Outlook 对象模型概述](../vsto/outlook-object-model-overview.md)   
 [如何：以编程方式按名称检索文件夹](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)  
  
  