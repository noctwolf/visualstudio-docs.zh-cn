---
title: “启动”命令 | Microsoft Docs
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
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6e70a682d9b9ef67e9f0372173c3396a0706cd2f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480530"
---
# <a name="start-command"></a>“启动”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[启动命令](https://docs.microsoft.com/visualstudio/ide/reference/start-command)。  
  
  
开始调试启动项目。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.Start [address]  
```  
  
## <a name="arguments"></a>自变量  
 `address`  
 可选。 程序挂起执行的地址，类似于源代码中的断点。 此参数仅在调试模式下有效。  
  
## <a name="remarks"></a>备注  
 “启动”命令在执行时会对指定的地址执行 RunToCursor 操作。  
  
## <a name="example"></a>示例  
 此示例启动调试器并忽略任何发生的异常。  
  
```  
>Debug.Start  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)



