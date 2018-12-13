---
title: 如何： 编辑 TableAdapter 查询 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vbData.Microsoft.VSDesigner.DataSource.DbSource
- vbdata.Microsoft.VSDesigner.DataSource.DbSource
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- queries [Visual Basic], editing
- TableAdapters, editing queries
- data [Visual Studio], TableAdapters
- editing queries
ms.assetid: aac7b7b4-bd91-4225-95d4-a07643568c43
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 687336b979ef7e6d46ea6deb4a5682f3aec065be
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49287893"
---
# <a name="how-to-edit-tableadapter-queries"></a>如何：编辑 TableAdapter 查询
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

编辑使用 TableAdapter 查询[编辑 Tableadapter](../data-tools/editing-tableadapters.md)中**数据集设计器**。 它不再满足你的应用程序的需求时，应修改 TableAdapter 查询。 （或者，您可以创建其他查询在 TableAdapter 上。 添加新的查询的详细信息，请参阅[如何： 创建 TableAdapter 查询](../data-tools/how-to-create-tableadapter-queries.md)。)  
  
> [!NOTE]
>  如果[TableAdapter 配置向导](http://msdn.microsoft.com/library/3a373dd9-7b34-4d3c-a48b-69414512bac8)而不是打开**TableAdapter 查询配置向导**，您可能选择 TableAdapter 的主`Fill`查询并不是一种TableAdapter 的其他查询。 为编辑 TableAdapter 的信息的主要`Fill`查询，请参阅[如何： 编辑 Tableadapter](http://msdn.microsoft.com/library/ca178745-e35a-45f1-a395-23cddfd8f855)。  
  
 ![使用多个查询的 TableAdapter](../data-tools/media/tableadapter.gif "TableAdapter")  
  
### <a name="to-edit-a-tableadapter-query"></a>若要编辑 TableAdapter 查询  
  
1.  打开中的数据集**数据集设计器**。 有关详细信息，请参阅[如何： 在数据集设计器中打开数据集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
2.  选择你想要编辑的 TableAdapter 查询。  
  
3.  右键单击 TableAdapter 查询并选择**配置**。  
  
     **TableAdapter 查询配置向导**随即打开，以便您进行修改的查询的存储的过程。  
  
4.  完成**TableAdapter 查询配置向导**与所需的更改。 有关详细信息，请参阅[编辑 Tableadapter](../data-tools/editing-tableadapters.md)。  
  
## <a name="see-also"></a>请参阅  
 [Tableadapter](http://msdn.microsoft.com/library/09416de9-134c-4dc7-8262-6c8d81e3f364)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)   
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)