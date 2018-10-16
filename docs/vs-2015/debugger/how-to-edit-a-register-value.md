---
title: 如何： 编辑寄存器值 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.register.edit
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- Registers window, editing register values
- register values
ms.assetid: e27b6bd8-e6d4-4f1d-8a86-9f4047bb1167
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6846fc8ae093f3f63a0b9caceee7d0a0c23767f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49196152"
---
# <a name="how-to-edit-a-register-value"></a>如何：编辑寄存器值
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

寄存器窗口是在启用了地址级调试时才可用**选项**对话框中，**调试**节点。  
  
### <a name="to-change-the-value-of-a-register"></a>更改寄存器值  
  
1.  在中**注册**窗口中，使用 TAB 键或鼠标，使插入点移动到你想要更改的值。 在开始键入之前，光标必须位于要覆盖的值之前。  
  
2.  键入新值。  
  
    > [!CAUTION]
    >  更改寄存器值（特别是 EIP 和 EBP 寄存器中的值）可能会影响程序的执行。  
  
    > [!CAUTION]
    >  编辑浮点值时，由于要将小数部分从十进制转换为二进制，因此所得的结果可能存在微小误差。 甚至看起来无关紧要的编辑都能引起浮点变量中某些最不重要的数据位发生变化。  
  
## <a name="see-also"></a>请参阅  
 [如何：使用“寄存器”窗口](../debugger/how-to-use-the-registers-window.md)





