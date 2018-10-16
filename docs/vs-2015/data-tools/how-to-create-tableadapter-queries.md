---
title: 如何： 创建 TableAdapter 查询 |Microsoft Docs
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
- TableAdapters, creating queries
- queries [Visual Studio], creating
- data [Visual Studio], TableAdapter queries
- queries [Visual Studio], TableAdapters
ms.assetid: df0cf4a5-e9cc-4de6-8b94-ce74fb7b2452
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: c4b800bcb70e41e1d80bf9a0a37d72f08f78c7a6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49195541"
---
# <a name="how-to-create-tableadapter-queries"></a>如何：创建 TableAdapter 查询
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

TableAdapter 查询是 SQL 语句或存储你的应用程序可以对数据库执行的过程。  
  
 添加到 TableAdapter 任意多个查询作为您的应用程序需要。 TableAdapter 查询显示为 TableAdapter 上的方法。 创建名为查询时`FillByCity`采用表示城市值的参数，将查询添加到 TableAdapter。 它添加为将作为参数的参数的正确类型的类型化方法 — 在本例中，表示城市值的字符串。 对任何对象调用任何方法一样 TableAdapter 查询。 例如，下面的代码执行`FillByCity`查询并填充`Customers`表的所有客户的城市值`Seattle`:  
  
 [!code-csharp[VbRaddataTableAdapters#1](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataTableAdapters/CS/Form1.cs#1)]
 [!code-vb[VbRaddataTableAdapters#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataTableAdapters/VB/Form1.vb#1)]  
  
 TableAdapter 查询可以填充数据表 (`Fill`并`FillBy`查询) 或返回使用由查询返回的数据填充的新数据表 (`GetData`和`GetDataBy`查询)。  
  
 您可以通过运行查询添加到现有 Tableadapter[编辑 Tableadapter](../data-tools/editing-tableadapters.md)。 (右键单击任何 TableAdapter，然后选择**添加查询**。)  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
## <a name="create-a-query-in-the-dataset-designer"></a>在数据集设计器中创建查询  
  
#### <a name="to-add-a-query-to-a-tableadapter-in-the-dataset-designer"></a>若要将查询添加到数据集设计器中的 TableAdapter  
  
1.  打开中的数据集**数据集设计器**。 有关详细信息，请参阅[如何： 在数据集设计器中打开数据集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
2.  右键单击所需的 TableAdapter，然后选择**添加查询**。  
  
     或  
  
3.  拖动**查询**从**数据集**选项卡**工具箱**拖到设计器上的表。  
  
     **TableAdapter 查询配置向导**随即打开。  
  
4.  完成向导。将查询添加到 TableAdapter。  
  
## <a name="create-a-query-directly-on-a-form-in-your-windows-application"></a>在 Windows 应用程序中的窗体上直接创建查询  
 如果你的窗体中对 TableAdapter 的实例可以添加查询使用[搜索标准生成器对话框](http://msdn.microsoft.com/library/0b306b92-f35e-45ef-a4be-3f653cd00c3d)，这会增加<xref:System.Windows.Forms.ToolStrip>到接受任何输入参数查询，所需的窗体控件，以及若要运行查询的按钮。  
  
#### <a name="to-add-a-query-to-a-tableadapter-using-the-search-criteria-dialog-box"></a>若要将查询添加到 TableAdapter 使用搜索条件对话框  
  
1.  在组件栏中选择一个 TableAdapter。  
  
2.  单击 TableAdapter 的智能标记，然后选择**添加查询**。  
  
3.  完成对话框中，并将查询添加到 TableAdapter。 有关详细信息，请参阅[搜索标准生成器对话框](http://msdn.microsoft.com/library/0b306b92-f35e-45ef-a4be-3f653cd00c3d)。  
  
## <a name="see-also"></a>请参阅  
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)   
 [如何： 编辑 TableAdapter 查询](../data-tools/how-to-edit-tableadapter-queries.md)   
 [创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)   
 [添加新数据源](../data-tools/add-new-data-sources.md)   
 [如何：连接到数据库中的数据](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [如何： 使用 Windows 窗体 BindingNavigator 控件导航数据](http://msdn.microsoft.com/library/0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb)   
 [演练： 在 Windows 窗体上显示数据](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [演练：创建带有多个查询的 TableAdapter](../data-tools/walkthrough-creating-a-tableadapter-with-multiple-queries.md)