---
title: 使用 n 层应用程序中的数据集 |Microsoft Docs
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
- datasets [Visual Basic], n-tier applications
- multi-tier database applications
- DataSet project [VS n-tier applications]
- distributed applications [VS n-tier applications]
- data [Visual Basic], n-tier applications
- TableAdapters, n-tier applications
- n-tier applications
- tiers, n-tier applications
- typed datasets, n-tier applications
- multiple tier applications
ms.assetid: f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d05204edfd7c3cd5daecad3a1cb21ba5ba7e60d8
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49205967"
---
# <a name="work-with-datasets-in-n-tier-applications"></a>在 n 层应用程序中使用数据集
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
N 层数据应用程序 * 是以数据为中心且分为多个逻辑层的应用程序 (或*层*)。 换句话说，N 层数据应用程序是分离到多个项目中的应用程序，数据访问层、业务逻辑层和表示层都在各自的项目中。 有关详细信息，请参阅[N 层数据应用程序概述](../data-tools/n-tier-data-applications-overview.md)。  
  
 类型化数据集经过改进，现在可以在相互独立的项目中生成 TableAdapter 和数据集类。 这使你可以快速分离各应用程序层及生成 N 层数据应用程序。  
  
 N 层中类型化数据集支持 n 层设计应用程序体系结构的迭代的开发。它还会删除手动将代码分离到多个项目的要求。 使用设计数据层的初始[创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)。 如果你已准备好好应用程序体系结构采用 n 层设计，设置**数据集项目**数据集以一个单独的项目中生成数据集类的属性。  
  
## <a name="in-this-section"></a>本节内容  
 [将数据集和 TableAdapter 分离到不同的项目中](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)  
 介绍如何将生成的数据集类移出包含生成的 TableAdapter 类的项目，并移入新的项目中。  
  
 [向 N 层应用程序中的 TableAdapter 添加代码](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)  
 介绍如何生成可以在其中为 N 层 TableAdapter 添加代码的分部类。  
  
 [向 N 层应用程序的数据集添加代码](../data-tools/add-code-to-datasets-in-n-tier-applications.md)  
 介绍如何生成可以在其中为 N 层数据集添加代码的分部类。  
  
 [向 N 层数据集添加验证](../data-tools/add-validation-to-an-n-tier-dataset.md)  
 介绍添加对更改数据执行验证的代码的位置。  
  
 [演练：创建 N 层数据应用程序](../data-tools/walkthrough-creating-an-n-tier-data-application.md)  
 提供有关创建类型化数据集并将 TableAdapter 和数据集代码分离到多个项目中的分步说明。  
  
 [演练： 向 N 层数据应用程序添加验证](http://msdn.microsoft.com/library/b35d072c-31f0-49ba-a225-69177592c265)  
 提供将验证添加到在 n 层数据应用程序演练中创建的应用程序的分步说明。  
  
## <a name="reference"></a>参考  
 <xref:System.Data.DataSet>  
  
 <xref:System.Data.TypedTableBase%601>  
  
## <a name="related-sections"></a>相关章节  
 [N 层数据应用程序概述](../data-tools/n-tier-data-applications-overview.md)  
  
 [分层更新](../data-tools/hierarchical-update.md)  
  
 [Visual Studio 中的数据集工具](../data-tools/dataset-tools-in-visual-studio.md)  
  
 [在 Visual Studio 中访问数据](../data-tools/accessing-data-in-visual-studio.md)  
  
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)  
  
 [使用 LINQ to SQL 的 N 层和远程应用程序](http://msdn.microsoft.com/library/854a1cdd-53cb-45f5-83ca-63962a9b3598)

