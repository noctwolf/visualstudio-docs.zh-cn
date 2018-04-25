---
title: “设置当前线程”命令 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.setcurrentthread
helpviewer_keywords:
- Set Current Thread command
- Debug.SetCurrentThread command
ms.assetid: 9917ed1d-6c30-4d94-b2f0-69acce74f1b2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d3a3ccd860088c38b84b805a54ee17d50240b2e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="set-current-thread-command"></a>“设置当前线程”命令
将指定的线程设置为当前线程。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.SetCurrentThread index  
```  
  
## <a name="arguments"></a>自变量  
 `index`  
 必须的。 按线程的索引选择线程。  
  
## <a name="example"></a>示例  
  
```  
>Debug.SetCurrentThread 1  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)