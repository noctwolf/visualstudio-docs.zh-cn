---
title: "Print 命令 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6eaf5d77da1dbc6e005764087dad338458e7ce8c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="print-command"></a>Print 命令
计算表达式或显示指定文本。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.Print text  
```  
  
## <a name="arguments"></a>参数  
 `text`  
 必需。 要计算的表达式或要显示的文本。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [计算机语句命令](../../ide/reference/evaluate-statement-command.md)   
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)