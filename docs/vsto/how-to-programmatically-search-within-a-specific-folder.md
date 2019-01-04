---
title: 如何：以编程方式在特定文件夹内的搜索
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook folders [Office development in Visual Studio], searching
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1427f0ab69cab2c23a0eeb7638bbc6e21778c55a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53915489"
---
# <a name="how-to-programmatically-search-within-a-specific-folder"></a>如何：以编程方式在特定文件夹内的搜索
  此代码示例使用`Find`并`FindNext`方法中的电子邮件的主题字段中搜索文本**收件箱**。 此方法使用字符串筛选器为要检查的起始字母的字母 T`Subject`文本。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>示例  
 [!code-csharp[Trin_OL_SearchFolder#1](../vsto/codesnippet/CSharp/Trin_OL_SearchFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>请参阅  
 [使用文件夹](../vsto/working-with-folders.md)   
 [Outlook 对象模型概述](../vsto/outlook-object-model-overview.md)   
 [如何：以编程方式按名称检索文件夹](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)  
