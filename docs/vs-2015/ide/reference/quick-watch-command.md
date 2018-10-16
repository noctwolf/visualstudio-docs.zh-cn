---
title: “快速监视”命令 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.quickwatch
helpviewer_keywords:
- Quick Watch command
- Debug.Quickwatch command
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: afe27d567601e43b10323f9dcc3417bcf15e9298
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269407"
---
# <a name="quick-watch-command"></a>“快速监视”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
在表达式字段中显示选定或指定的文本[快速监视对话框中](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)。 可使用此对话框计算调试器所识别的变量或表达式的当前值或计算寄存器的内容。 此外，可更改任何非常量变量的值或任何寄存器的内容。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.QuickWatchq [text]  
```  
  
## <a name="arguments"></a>自变量  
 `text`  
 可选。 要添加到“快速监视”对话框的文本。  
  
## <a name="remarks"></a>备注  
 如果忽略了 `text`，则光标处当前选中的文本或字词将添加到“监视”窗口。  
  
## <a name="example"></a>示例  
  
```  
>Debug.QuickWatch  
```  
  
## <a name="see-also"></a>请参阅  
 [如何： 使用快速监视对话框](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



