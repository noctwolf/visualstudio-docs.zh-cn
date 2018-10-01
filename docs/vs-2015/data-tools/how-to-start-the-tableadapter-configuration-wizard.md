---
title: 如何： 启动 TableAdapter 配置向导 |Microsoft Docs
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
- TableAdapters, Configuration Wizard
- TableAdapter Configuration Wizard
ms.assetid: 301f2dcd-ed72-4229-80ef-3b59cb062d5d
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 0cf7d3e5ace98ac73f97909b184ce04b86d4b9ee
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477912"
---
# <a name="how-to-start-the-tableadapter-configuration-wizard"></a>如何：启动 TableAdapter 配置向导
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**TableAdapter 配置向导**创建并编辑 Tableadapter 中强类型化数据集。 该向导根据输入到向导中的 SQL 语句或数据库中现有的存储过程来创建 TableAdapter。 该向导还可以根据输入到向导中的 SQL 语句在数据库中创建新的存储过程。  
  
### <a name="to-start-the-tableadapter-configuration-wizard-to-create-a-new-tableadapter"></a>启动 TableAdapter 配置向导创建新的 TableAdapter  
  
1.  打开中的数据集**数据集设计器**。 有关详细信息，请参阅[如何： 在数据集设计器中打开数据集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
    > [!NOTE]
    >  如果在项目中没有数据集，请参阅[创建和配置数据集](../data-tools/create-and-configure-datasets-in-visual-studio.md)。  
  
2.  如果要创建新的 TableAdapter，拖动**TableAdapter**对象从**数据集**选项卡**工具箱**拖到**数据集设计器**.  
  
3.  上**选择数据连接**页上，从当前可用连接列表中选择一个数据连接或选择**新的连接**若要创建新的连接。  
  
### <a name="to-start-the-tableadapter-configuration-wizard-to-edit-an-existing-tableadapter"></a>启动 TableAdapter 配置向导编辑现有 TableAdapter  
  
1.  打开中的数据集**数据集设计器**。 有关详细信息，请参阅[如何： 在数据集设计器中打开数据集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
2.  右键单击在 TableAdapter**数据集设计器**，然后选择**配置**。 向导将打开到**生成 SQL 语句**页或**将命令绑定到现有存储过程**页上，具体取决于最初配置 TableAdapter 的方式。  
  
3.  完成向导。  
  
## <a name="see-also"></a>请参阅  
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)   
 [创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)   
 [添加新数据源](../data-tools/add-new-data-sources.md)   
 [如何：连接到数据库中的数据](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [如何： 进行排序和筛选 ADO.NET 数据使用 Windows 窗体 BindingSource 组件](http://msdn.microsoft.com/library/6c206daf-d706-4602-9dbe-435343052063)   
 [如何： 使用 Windows 窗体 BindingSource 组件创建查找表](http://msdn.microsoft.com/library/622fce80-879d-44be-abbf-8350ec22ca2b)   
 [演练：在 Windows 窗体上显示数据](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)