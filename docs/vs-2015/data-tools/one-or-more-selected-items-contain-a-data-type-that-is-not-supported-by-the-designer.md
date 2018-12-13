---
title: 一个或多个选定的项包含设计器不支持的数据类型 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71dcd4f9-2946-42c5-9ce4-99c819ea2785
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 640dd69990e3c659efe98ef5e73ae83098c58c1a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49176966"
---
# <a name="one-or-more-selected-items-contain-a-data-type-that-is-not-supported-by-the-designer"></a>一个或多个所选项包含设计器不支持的数据类型
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
从一个或多个项拖动**服务器资源管理器**/**数据库资源管理器**拖动到[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]包含不支持的数据类型[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]（例如，[CLR 用户定义类型](http://msdn.microsoft.com/library/9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2))。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1.  创建一个基于所需的表的视图，且其中不包括不支持的数据类型。  
  
2.  将从该视图**服务器资源管理器**/**数据库资源管理器**拖到设计器。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [演练： 创建 LINQ to SQL 类 （O-R 设计器）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)

