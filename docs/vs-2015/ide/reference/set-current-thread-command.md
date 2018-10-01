---
title: “设置当前线程”命令 | Microsoft Docs
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
- debug.setcurrentthread
helpviewer_keywords:
- Set Current Thread command
- Debug.SetCurrentThread command
ms.assetid: 9917ed1d-6c30-4d94-b2f0-69acce74f1b2
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ccacc3c6f6b09401fcce52ef2530ccf7dd4746cd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471915"
---
# <a name="set-current-thread-command"></a>“设置当前线程”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[设置当前线程的命令](https://docs.microsoft.com/visualstudio/ide/reference/set-current-thread-command)。  
  
  
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



