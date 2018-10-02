---
title: 断点时命中对话框 |Microsoft Docs
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
- vs.debug.whenbreakpointishit
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- SQL
- VB
- CSharp
- C++
ms.assetid: 476e3d98-cf35-4338-b124-cd0f3010d854
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 650e390abde6f3ad99e5a0c30591c8d1530df692
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477870"
---
# <a name="when-breakpoint-is-hit-dialog-box"></a>“命中断点时”对话框
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[时是按断点对话框](https://docs.microsoft.com/visualstudio/debugger/when-breakpoint-is-hit-dialog-box)。  
  
使用此对话框，您可以自定义命中断点时，会发生的操作。  
  
## <a name="uielement-list"></a>UIElement 列表  
 **打印一条消息**  
 打印一条消息，使用 DebuggerDisplay 语法。 有关详细信息，请参阅[使用 DebuggerDisplay 特性](../debugger/using-the-debuggerdisplay-attribute.md)。  
  
 此文本框还支持可用于单独或 DebuggerDisplay 表达式的大括号内的特殊关键字 （如 $ADDRESS)。 在对话框中列出了可用的关键字。  
  
 **继续执行**  
 启用此控件时，才**打印一条消息**处于选中状态。 选择此控件，可以使用断点与跟踪点跟踪程序执行，而不是重大时命中位置。  
  
## <a name="see-also"></a>请参阅  
 [使用断点](../debugger/using-breakpoints.md)   
 [使用 DebuggerDisplay 特性](../debugger/using-the-debuggerdisplay-attribute.md)



