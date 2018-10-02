---
title: 如何： 在 Windows 中的数据窗体应用程序中显示相关 |Microsoft Docs
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
- Windows Forms, displaying data
- displaying data, related data
- related data, displaying
- displaying tables, related data
- data [Windows Forms], displaying
- displaying table data
- data [Windows Forms], related
- displaying data on forms, related data
- displaying table information
ms.assetid: 60b1f1ec-6257-42ab-83f0-06d54ed364fd
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: fc62789860cc10f5c410849936715a8ef82eae3f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482302"
---
# <a name="how-to-display-related-data-in-a-windows-forms-application"></a>如何：在 Windows 窗体应用程序中显示相关数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可以通过将某些项共享相同的主表节点，从显示相关的数据[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)拖动到窗体。 例如，如果有一个数据源具有`Customers`表和相关`Orders`表中，您会看到这两个表为顶级节点 （在树视图中） 中**数据源**窗口。 展开`Customers`节点，以便您可以看到的列，并你将注意到列表中的最后一列是可展开节点表示`Orders`表。 此节点表示客户的相关的订单。 这意味着如果你想要创建窗体，您可以选择一个客户，然后显示该客户的订单列表，则会将你想要显示此单一层次结构中的项。  
  
 ![显示关系数据源窗口](../data-tools/media/datasources2.gif "DataSources2")  
创建显示相关的记录的数据绑定控件  
  
 ![视频链接](../data-tools/media/playvideo.gif "播放视频")本主题的视频版本，请参阅[如何： 更新相关表](http://go.microsoft.com/fwlink/?LinkId=143527)。  
  
### <a name="to-create-controls-that-display-related-records"></a>若要创建显示相关的记录的控件  
  
1.  打开在窗体[Windows 窗体设计器](http://msdn.microsoft.com/en-us/3c3d61f8-f36c-4d41-b9c3-398376fabb15)。  
  
2.  打开**数据源**窗口。 有关详细信息，请参阅[如何： 打开数据源窗口](../data-tools/how-to-open-the-data-sources-window.md)。  
  
3.  展开表示关系中的父表的节点。 （父表是一个对多关系的"一"方上的表。）  
  
4.  将你想要从关系中的父表中显示任何的项拖**数据源**窗口拖到窗体上的。  
  
5.  相关的子表显示为父表的列列表底部的可展开节点。 将你想要显示的此类的相关节点拖动到窗体的项。  
  
    > [!NOTE]
    >  从顶级节点拖动项创建一个不相关的单独[BindingSource 组件](http://msdn.microsoft.com/library/3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9)的并不促成导航相关的记录。 若要将绑定相关的数据必须从同一层次结构节点中选择的表。  
  
## <a name="see-also"></a>请参阅  
 [数据演练](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [演练： 在 Windows 窗体上显示数据](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [TableAdapter 概述](../data-tools/tableadapter-overview.md)   
 [创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)   
 [添加新数据源](../data-tools/add-new-data-sources.md)   
 [如何：连接到数据库中的数据](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [验证数据](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)   
 [如何：使用 Windows 窗体 BindingNavigator 控件导航数据](http://msdn.microsoft.com/library/0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb)