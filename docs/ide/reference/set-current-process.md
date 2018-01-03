---
title: "设置当前进程 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eb673db29a4bb106aa4c9c4d9022293367e8ed4f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="set-current-process"></a>设置当前进程
将指定的进程设置为调试器中的活动进程。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.SetCurrentProcess index  
```  
  
## <a name="arguments"></a>自变量  
 `index`  
 必须的。 进程的索引。  
  
## <a name="remarks"></a>备注  
 调试时可以附加到多个进程，但在任何给定时间，调试器中只有一个进程处于活动状态。 可以使用 `SetCurrentProcess` 命令设置活动进程。  
  
## <a name="example"></a>示例  
  
```  
>Debug.SetCurrentProcess 1  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)