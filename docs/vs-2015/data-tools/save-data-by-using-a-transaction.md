---
title: 使用事务保存数据 |Microsoft Docs
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
- saving data, using transactions
- System.Transactions namespace
- transactions, saving data
- data [Visual Studio], saving
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c88bd18e8b02c62a31743427bf70cc7eac68ed79
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476678"
---
# <a name="save-data-by-using-a-transaction"></a>使用事务保存数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[使用事务保存数据](https://docs.microsoft.com/visualstudio/data-tools/save-data-by-using-a-transaction)。  
  
  
您将数据保存在事务中的使用<xref:System.Transactions>命名空间。 使用<xref:System.Transactions.TransactionScope>对象能够参与为您自动管理的事务。  
  
 项目不会创建对 System.Transactions 程序集的引用，因此您需要手动添加对项目使用事务的引用。  
  
> [!NOTE]
>  <xref:System.Transactions>在 Windows 2000 或更高版本支持命名空间。  
  
 若要实现事务的最简单方法是实例化<xref:System.Transactions.TransactionScope>对象中`using`语句。 (有关详细信息，请参阅[Using 语句](http://msdn.microsoft.com/library/665d1580-dd54-4e96-a9a9-6be2a68948f1)，并[using 语句](http://msdn.microsoft.com/library/afc355e6-f0b9-4240-94dd-0d93f17d9fc3)。)在中运行的代码`using`语句参与事务。  
  
 若要提交事务，调用<xref:System.Transactions.TransactionScope.Complete%2A>方法中使用的最后一个语句块。  
  
 若要回滚事务，会引发异常之前调用<xref:System.Transactions.TransactionScope.Complete%2A>方法。  
  
 有关详细信息，请参阅[将数据保存在事务中](../data-tools/save-data-in-a-transaction.md)。  
  
### <a name="to-add-a-reference-to-the-systemtransactions-dll"></a>若要添加对 System.Transactions dll 的引用  
  
1.  上**项目**菜单中，选择**添加引用**。  
  
2.  上 **.NET**选项卡 (**SQL Server** SQL Server 项目的选项卡)，选择**System.Transactions**，并选择下列**确定**。  
  
     System.transactions.dll 的引用添加到项目。  
  
### <a name="to-save-data-in-a-transaction"></a>若要将数据保存在事务中  
  
-   添加代码以保存中使用的数据包含的事务的语句。 下面的代码演示如何创建并实例化<xref:System.Transactions.TransactionScope>对象中的 using 语句：  
  
     [!code-csharp[VbRaddataSaving#11](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form2.cs#11)]
     [!code-vb[VbRaddataSaving#11](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form2.vb#11)]  
  
## <a name="see-also"></a>请参阅  
 [将数据保存回数据库](../data-tools/save-data-back-to-the-database.md)

