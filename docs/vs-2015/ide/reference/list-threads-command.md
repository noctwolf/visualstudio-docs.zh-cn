---
title: “列出线程”命令 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.listthreads
helpviewer_keywords:
- ListThreads command
- list threads command
- Debug.ListThreads command
ms.assetid: 34b665c0-d46f-4c1a-a066-b678eba5ac54
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cd8e9f96e0f477ba0b83419274d9b2ed0a101195
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480988"
---
# <a name="list-threads-command"></a>“列出线程”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[列出线程命令](https://docs.microsoft.com/visualstudio/ide/reference/list-threads-command)。  
  
  
显示当前程序中线程的列表。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.ListThreads [index]  
```  
  
## <a name="arguments"></a>自变量  
 `index`  
 可选。 通过索引来选择要用作当前线程的线程。  
  
## <a name="remarks"></a>备注  
 如果已指定，`index` 实际参数将指示的线程标记为当前线程。 星号 (*) 显示在当前线程旁边的列表中。  
  
## <a name="example"></a>示例  
  
```  
>Debug.ListThreads   
```  
  
## <a name="see-also"></a>请参阅  
 [“列出调用堆栈”命令](../../ide/reference/list-call-stack-command.md)   
 [“列出反汇编”命令](../../ide/reference/list-disassembly-command.md)   
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)



