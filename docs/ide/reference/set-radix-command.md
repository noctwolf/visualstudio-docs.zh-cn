---
title: “设置基数”命令 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.setradix
helpviewer_keywords:
- Set Radix command
- Debug.SetRadix command
ms.assetid: 6ffd1554-7530-4da4-b5f5-e276a5034f3b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9e09b4d2673dda2e288915f36ff5d520aa5423c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="set-radix-command"></a>“设置基数”命令
设置或返回用来显示整数值的数值基数。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.SetRadix [10 | 16 | hex | dec]  
```  
  
## <a name="arguments"></a>自变量  
 `10` 或 `16` 或 `hex` 或 `dec`  
 可选。 指示十进制（10 或 dec）或十六进制（16 或 hex）。 如果省略某个参数，则返回当前基数值。  
  
## <a name="example"></a>示例  
 此示例将环境设置为以十六进制格式显示整数值。  
  
```  
>Debug.SetRadix hex  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio 命令别名](../../ide/reference/visual-studio-command-aliases.md)