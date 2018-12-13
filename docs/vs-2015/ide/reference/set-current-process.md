---
title: 设置当前进程 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0baea39c341e8034ff222de32548d0518f115e82
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49246657"
---
# <a name="set-current-process"></a>设置当前进程
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
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
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



