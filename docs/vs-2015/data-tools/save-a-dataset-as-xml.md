---
title: 将数据集另存为 XML |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- XML [Visual Basic], datasets
- data [Visual Studio], saving as XML
- datasets [Visual Basic], saving as XML
- saving data
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bfea6a97dd5126216d5163dee1dc17e5f6364b46
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468937"
---
# <a name="save-a-dataset-as-xml"></a>将数据集另存为 XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[将数据集另存为 XML](https://docs.microsoft.com/visualstudio/data-tools/save-a-dataset-as-xml)。  
  
  
可以通过在数据集上调用提供的 XML 方法访问 XML 数据集中的数据。 若要以 XML 格式保存数据，您可以调用<xref:System.Data.DataSet.GetXml%2A>方法或<xref:System.Data.DataSet.WriteXml%2A>方法的<xref:System.Data.DataSet>。  
  
 调用<xref:System.Data.DataSet.GetXml%2A>方法返回一个字符串，包含格式为 XML 在数据集中的所有数据表中的数据。  
  
 调用<xref:System.Data.DataSet.WriteXml%2A>方法将 XML 格式的数据发送到你指定的文件。  
  
### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>若要在数据集中的数据以 XML 形式保存到变量  
  
-   <xref:System.Data.DataSet.GetXml%2A>方法将返回<xref:System.String>。这意味着声明类型的变量<xref:System.String>并将其分配的结果<xref:System.Data.DataSet.GetXml%2A>方法。  
  
     [!code-csharp[VbRaddataSaving#12](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#12)]
     [!code-vb[VbRaddataSaving#12](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#12)]  
  
### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>若要将数据集中的数据以 XML 形式保存到文件  
  
-   <xref:System.Data.DataSet.WriteXml%2A>方法有若干重载。 下面的代码演示如何将数据保存到文件。声明一个变量并将其分配有效的路径保存到文件。  
  
     [!code-csharp[VbRaddataSaving#13](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#13)]
     [!code-vb[VbRaddataSaving#13](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>请参阅  
 [将数据保存回数据库](../data-tools/save-data-back-to-the-database.md)

