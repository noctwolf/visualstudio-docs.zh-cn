---
title: T4 CleanUpBehavior 指令 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e5a211f-a3bf-4229-bff0-7d2e45b71c64
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: ee1882b6b63dbb2729070d32fcee7c1e58d280c5
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49263391"
---
# <a name="t4-cleanupbehavior-directive"></a>T4 CleanUpBehavior 指令
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

若要在处理文本模板之后删除 appDomain，请包括以下行：  
  
```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 文本模板是在独立于主机进程之外的 appDomain 中进行处理的。 在大多数情况下，在处理了一个文本模板之后，则将再次使用 appdomain 处理下一个模板。 但如果你指定 CleanupBehavior，则将删除 appDomain 并且将在新的 appDomain 中处理下一个模板。  
  
 这将减慢文本处理的速度，但可用于确保释放资源。  
  
 此指令将仅在 Visual Studio 主机中起作用。



