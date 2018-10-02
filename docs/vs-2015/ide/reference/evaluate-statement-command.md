---
title: “计算语句”命令 | Microsoft Docs
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
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d569033193997135d9d0bc990ab7b9a9ef815f8d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472446"
---
# <a name="evaluate-statement-command"></a>“计算语句”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[评估语句命令](https://docs.microsoft.com/visualstudio/ide/reference/evaluate-statement-command)。  
  
  
计算并显示给定的语句。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.EvaluateStatement text   
```  
  
## <a name="arguments"></a>自变量  
 `text`  
 必须的。 要评估的语句。  
  
## <a name="remarks"></a>备注  
 用于输入 EvaluateStatement 命令的窗口确定是将等号 (=) 解释为比较运算符还是赋值运算符。  
  
 在“命令”窗口中，将等号 (=) 解释为比较运算符。 例如，如果变量 `a` 和 `b` 的值不同，则命令  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 将返回 `false` 的值。  
  
 与此相反，在“即时”窗口中，将等号 (=) 解释为赋值运算符。 例如，命令  
  
```  
>Debug.EvaluateStatement(a=b)  
```  
  
 将为变量 `a` 赋予变量 `b` 的值。  
  
## <a name="example"></a>示例  
  
```  
>Debug.EvaluateStatement(a+b)  
```  
  
## <a name="see-also"></a>请参阅  
 [“打印”命令](../../ide/reference/print-command.md)   
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)



