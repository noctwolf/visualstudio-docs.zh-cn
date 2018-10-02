---
title: 如何查明谁在传递错误的参数值？ | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.parameters
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], parameters
- parameters [debugger]
- passing parameters, troubleshooting wrong values
- functions [debugger], detecting wrong parameter values
- parameter values, troubleshooting
ms.assetid: 1f1ae455-0e25-4e9d-b33f-53908f5bd6ce
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1d7ae67e7ba09a25277afc55ef92da47a8e770d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471470"
---
# <a name="how-can-i-find-out-who-is-passing-a-wrong-parameter-value"></a>如何查明谁在传递错误的参数值？
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何查明在传递了错误的参数值？](https://docs.microsoft.com/visualstudio/debugger/how-can-i-find-out-who-is-passing-a-wrong-parameter-value-q)。  
  
问题描述  
 给我的某个函数传递的是错误的参数值。 很多地方都在调用该函数。 如何查明是谁在传递错误值？  
  
## <a name="solution"></a>解决方案  
  
#### <a name="to-resolve-this-problem"></a>解决此问题  
  
1.  在函数的开始处设置一个位置断点。  
  
2.  右键单击断点并选择**条件**。  
  
3.  在中**断点条件**对话框中，单击**条件**复选框。 请参阅[高级断点](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)。  
  
4.  在文本框中输入一个表达式（例如 `Var==3`），此处 `Var` 是包含错误值的参数的名称，`3` 是传给此参数的错误值。  
  
5.  选择**为 True**单选按钮，然后单击**确定**按钮。  
  
6.  现在再次运行程序。 当 `Var` 参数的值为 `3` 时，断点导致程序在函数开始处暂停。  
  
7.  然后可以使用“调用堆栈”窗口查找调用函数并定位到其源代码。 有关详细信息，请参阅[如何： 使用调用堆栈窗口](../debugger/how-to-use-the-call-stack-window.md)。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)   
 [断点](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [调试本机代码](../debugger/debugging-native-code.md)



