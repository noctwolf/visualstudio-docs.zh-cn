---
title: 如何： 应用编辑在中断模式下使用编辑并继续 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [Visual Basic], applying edits in break mode
- break mode, applying code changes
- Edit and Continue, applying edits in break mode
- editing, break mode
- coding, editing in break mode
- code, editing in break mode
ms.assetid: 1eef7498-6a1f-4fba-8146-510adc6375c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f45b2a64e7602d038a12f436019a8f99e352aa26
ms.sourcegitcommit: a7de99f36e9ead7ea9e9bac23c88d05ddfc38b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2018
ms.locfileid: "52257065"
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue-visual-basic"></a>如何： 应用编辑在中断模式下使用编辑并继续 (Visual Basic)
可以在中断模式下使用“编辑并继续”编辑代码，然后不必停止和重新启动执行即可继续。  
  
有关使用编辑并继续调试时的限制，请参阅[支持的代码更改 (C#和 Visual Basic](../debugger/supported-code-changes-csharp.md)]
  
### <a name="to-edit-code-in-break-mode"></a>在中断模式下编辑代码  
  
1.  执行下列操作之一进入中断模式：  
  
    -   在代码中设置断点，然后选择**开始调试**从**调试**菜单，然后等待应用程序命中断点。  
  
         或  
  
    -   开始调试，然后依次**全部中断**从**调试**菜单。  
  
         或  
  
    -   异常发生时，选择**启用编辑**上**异常助手**。  
  
2.  进行任何所需和受支持的代码更改。  
  
     有关详细信息，请参阅[支持的代码更改 (C#和 Visual Basic](../debugger/supported-code-changes-csharp.md)。  
  
    > [!NOTE]
    >  如果尝试进行“编辑并继续”所不允许的代码更改，你的编辑将被加上紫色波浪线，并且“任务列表”中会出现一项任务。 除非撤消非法的代码更改，否则将无法继续执行代码。  
  
3.  上**调试**菜单上，单击**继续**继续执行。  
  
     在你所做的编辑已并入项目并已应用的情况下，你的代码继续执行。  
  
## <a name="see-also"></a>请参阅  
 [支持代码更改 (C#和 Visual Basic](../debugger/supported-code-changes-csharp.md)   
 [编辑并继续 (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)