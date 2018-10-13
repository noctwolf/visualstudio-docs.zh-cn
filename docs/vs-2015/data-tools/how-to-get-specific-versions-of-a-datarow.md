---
title: 如何： 获取 DataRow 的特定版本 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
- row states
- updating datasets, row states
- DataRow object
ms.assetid: d7cde25e-cef5-4559-b994-be00e258ac1f
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 5bd8ae12c77c671e375043a0381a4b580d1a03d7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49255477"
---
# <a name="how-to-get-specific-versions-of-a-datarow"></a>如何：获取 DataRow 的特定版本
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

数据集时对数据行进行了更改，将保留原始 (<xref:System.Data.DataRowVersion>) 和新 (<xref:System.Data.DataRowVersion>) 行的版本。 例如，之前调用`AcceptChanges`方法，你的应用程序可以访问一条记录的不同版本 (如中所定义<xref:System.Data.DataRowVersion>枚举) 并相应地处理所做的更改。  
  
> [!NOTE]
>  行的不同版本存在已编辑之后，并在它必须仅`AcceptChanges`调用方法。 之后`AcceptChanges`调用方法、 当前和原始版本都相同。  
  
 传递<xref:System.Data.DataRowVersion>值的列索引 （或字符串形式的列名称） 以及返回该列的特定行版本中的值。 期间标识已更改的列<xref:System.Data.DataTable.ColumnChanging>和<xref:System.Data.DataTable.ColumnChanged>事件，这就是检查不同行的好时机行出于验证目的的版本。 但是，如果暂时挂起了约束，不会引发这些事件，并将需要以编程方式确定哪些列发生了更改。 您可以执行此操作，可以循环访问<xref:System.Data.DataTable.Columns%2A>集合并比较不同<xref:System.Data.DataRowVersion>值。  
  
## <a name="accessing-the-original-version-of-a-datarow"></a>访问 DataRow 的原始版本  
  
#### <a name="to-get-the-original-version-of-a-record"></a>若要获取一条记录的原始版本  
  
-   访问传入的列的值<xref:System.Data.DataRowVersion>你想要返回的行。  
  
     下面的示例演示如何使用<xref:System.Data.DataRowVersion>若要获取的原始值的值`CompanyName`字段中<xref:System.Data.DataRow>:  
  
     [!code-csharp[VbRaddataEditing#21](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#21)]
     [!code-vb[VbRaddataEditing#21](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#21)]  
  
## <a name="accessing-the-current-version-of-a-datarow"></a>访问数据行的当前版本  
  
#### <a name="to-get-the-current-version-of-a-record"></a>若要获取一条记录的当前版本  
  
-   访问的列的值并将参数添加到索引，指示你想要返回的行版本。  
  
     下面的示例演示如何使用<xref:System.Data.DataRowVersion>要获取的当前值的值`CompanyName`字段中<xref:System.Data.DataRow>:  
  
     [!code-csharp[VbRaddataEditing#22](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#22)]
     [!code-vb[VbRaddataEditing#22](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#22)]  
  
## <a name="see-also"></a>请参阅  
 [编辑你的应用程序中的数据](../data-tools/editing-data-in-your-application.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [保存数据](../data-tools/saving-data.md)   
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [在 Visual Studio 中的数据应用程序的概述](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [连接到 Visual Studio 中的数据](../data-tools/connecting-to-data-in-visual-studio.md)   
 [准备应用程序以接收数据](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [将数据提取到你的应用程序](../data-tools/fetching-data-into-your-application.md)   
 [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)