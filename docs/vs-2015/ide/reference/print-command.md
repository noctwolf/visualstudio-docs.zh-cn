---
title: Print 命令 | Microsoft Docs
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
- debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e518b3c6ffc3520b408e7c1bfb1fd1703e40a8de
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472012"
---
# <a name="print-command"></a>Print 命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[Print 命令](https://docs.microsoft.com/visualstudio/ide/reference/print-command)。  
  
  
计算表达式或显示指定文本。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.Print text  
```  
  
## <a name="arguments"></a>自变量  
 `text`  
 必须的。 要计算的表达式或要显示的文本。  
  
## <a name="remarks"></a>备注  
 可使用问号 (?) 作为此命令的别名。 例如，命令  
  
```  
>Debug.Print expA  
```  
  
 也可写作  
  
```  
>? expA  
```  
  
 此命令的这两个版本都将返回表达式 `expA` 的当前值。  
  
## <a name="example"></a>示例  
  
```  
>Debug.Print varA  
```  
  
## <a name="see-also"></a>请参阅  
 [计算机语句命令](../../ide/reference/evaluate-statement-command.md)   
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)



