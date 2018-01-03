---
title: -Diff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 14deeec64d4645135f19587997844bfdd0b18cd5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="diff"></a>/Diff
比较两个文件。 差异将在特殊 Visual Studio 窗口中显示。  
  
## <a name="syntax"></a>语法  
  
```  
devenv /Diff SourceFile, TargetFile, [SourceDisplayName],[TargetDisplayName]  
```  
  
## <a name="arguments"></a>自变量  
 `SourceFile`  
 必须的。 要比较的第一个文件的完整路径和名称。  
  
 `TargetFile`  
 必须的。 要比较的第二个文件的完整路径和名称  
  
 `SourceDisplayName`  
 可选。 第一个文件的显示名称。  
  
 `TargetDisplayName`  
 可选。 第二个文件的显示名称。