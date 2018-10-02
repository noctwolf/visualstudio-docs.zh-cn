---
title: 将数据保存 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DataRow.RowState
- DataSet.GetChanges
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- DBDirect methods
- updating data
- data [Visual Studio], saving
- TableAdapter DBDirect methods
- databases, updating
- TableAdapter.Update method
- data [Visual Studio], updating
- saving data
- updating databases
ms.assetid: 21d2b115-62e4-4ac9-a873-dcbb535b8af8
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 14ff0e62608c3e2ab0c72366d9544f1d1309737a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483138"
---
# <a name="saving-data"></a>保存数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

保存数据是持久保存的过程更改回原始数据存储，通常为关系数据库 SQL Server 等应用程序的数据模型中的数据。  
  
 通过数据模型中更新数据源通常是一个两步过程。 第一步是使用新信息更新数据模型-新记录已更改的记录，或已删除的记录。 第二步是将更改保存回数据库在数据模型中。  
  
 以下主题介绍的概念和任务与保存数据相关联。  
  
## <a name="related-topics"></a>相关主题  
 [将数据保存回数据库](../data-tools/save-data-back-to-the-database.md)  
 提供了如何在数据集中进行更改和数据集将这些更改保存到数据库以跟踪更改的信息的方式的概述。  
  
 [保存实体数据](../data-tools/saving-entity-data.md)  
 介绍如何将更改保存在[ADO.NET 实体框架](http://msdn.microsoft.com/library/a437041f-6899-4ae7-96ce-aabf528d7205)并[WCF 数据服务 4.5](http://msdn.microsoft.com/library/73d2bec3-7c92-4110-b905-11bb0462357a)应用程序。