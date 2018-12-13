---
title: 如何： 创建映射到存储的过程和函数 （O-R 设计器） 的 DataContext 方法 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8b1864fa87867d2f48179c5215a18f2897d9883c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49196191"
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>如何： 创建映射到存储的过程和函数 （O/R 设计器） 的 DataContext 方法
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
存储的过程和函数可以添加到[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]作为<xref:System.Data.Linq.DataContext>方法。 调用该方法并传入所需参数将对数据库运行存储过程或函数，并返回 <xref:System.Data.Linq.DataContext> 方法的返回类型的数据。 有关详细信息<xref:System.Data.Linq.DataContext>方法，请参阅[DataContext 方法 （O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)。  
  
> [!NOTE]
>  将更改从实体类保存到数据库时，还可以使用存储过程重写执行插入、更新和删除操作的默认 [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] 运行时行为。 有关详细信息，请参阅[如何： 分配存储的过程以便执行更新、 插入和删除操作 （O/R 设计器）](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)。  
  
## <a name="creating-datacontext-methods"></a>创建 DataContext 方法  
 您可以创建<xref:System.Data.Linq.DataContext>方法通过拖动存储过程或函数从**服务器资源管理器/数据库资源管理器**拖动到[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]。  
  
> [!NOTE]
>  根据在 <xref:System.Data.Linq.DataContext>上放置存储过程或函数的位置不同，生成的 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] 方法的返回类型也有所不同。 如果直接将项放在现有实体类上，则将创建具有该实体类返回类型的 <xref:System.Data.Linq.DataContext> 方法。 如果将项放在 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]的空白区域，则将创建返回自动生成类型的 <xref:System.Data.Linq.DataContext> 方法。 在将 <xref:System.Data.Linq.DataContext> 方法添加到方法窗格后可以更改该方法的返回类型。 若要检查或更改的返回类型<xref:System.Data.Linq.DataContext>方法中，选择它，并检查**返回类型**中的属性**属性**窗口。 有关详细信息，请参阅[如何： 更改 DataContext 方法 （O/R 设计器） 的返回类型](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>创建返回自动生成类型的 DataContext 方法  
  
1.  在中**服务器资源管理器**/**数据库资源管理器**，展开**存储过程**你正在使用的数据库的节点。  
  
2.  找到所需的存储过程并将其拖到 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]的空白区域。  
  
     <xref:System.Data.Linq.DataContext>方法创建具有自动生成的返回类型，并出现在**方法**窗格。  
  
#### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>创建具有实体类的返回类型的 DataContext 方法  
  
1.  在中**服务器资源管理器**/**数据库资源管理器**，展开**存储过程**你正在使用的数据库的节点。  
  
2.  找到所需的存储过程并将其拖到 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]中的一个现有实体类上。  
  
     <xref:System.Data.Linq.DataContext>方法创建具有所选的实体类返回类型，并出现在**方法**窗格。  
  
> [!NOTE]
>  有关更改返回类型的现有<xref:System.Data.Linq.DataContext>方法，请参阅[如何： 更改 DataContext 方法 （O/R 设计器） 的返回类型](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [DataContext 方法 （O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)   
 [演练： 创建 LINQ to SQL 类 （O-R 设计器）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Visual Basic 中的 LINQ 简介](http://msdn.microsoft.com/library/3047d86e-0d49-40e2-928b-dc02e46c7984)   
 [如何：在 C# 中编写 LINQ 查询](http://msdn.microsoft.com/library/45e47fcc-cfa1-4b72-b161-d038ae87bd23)

