---
title: 如何： 在应用编辑中断模式下的使用编辑并继续 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 37c172c49132f8080dc29040fa7325c19f1871f1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>如何：使用“编辑并继续”在中断模式下应用编辑
可以在中断模式下使用“编辑并继续”编辑代码，然后不必停止和重新启动执行即可继续。  
  
在将编辑并继续使用在调试时的限制，请参阅[支持的代码更改 (C# 和 Visual Basic](../debugger/supported-code-changes-csharp.md)]
  
### <a name="to-edit-code-in-break-mode"></a>在中断模式下编辑代码  
  
1.  执行下列操作之一进入中断模式：  
  
    -   在代码中，设置断点，然后选择**启动调试**从**调试**菜单，然后等待应用程序命中断点。  
  
         -或-  
  
    -   启动调试，，然后选择**全部中断**从**调试**菜单。  
  
         -或-  
  
    -   发生异常时，选择**启用编辑**上**异常助手**。  
  
2.  进行所需的并且受支持的代码更改。  
  
     有关详细信息，请参阅[支持的代码更改 (C# 和 Visual Basic](../debugger/supported-code-changes-csharp.md)。  
  
    > [!NOTE]
    >  如果尝试进行“编辑并继续”所不允许的代码更改，你的编辑将被加上紫色波浪线，并且“任务列表”中会出现一项任务。 除非撤消非法的代码更改，否则将无法继续执行代码。  
  
3.  上**调试**菜单上，单击**继续**若要继续执行。  
  
     在你所做的编辑已并入项目并已应用的情况下，你的代码继续执行。  
  
## <a name="see-also"></a>另请参阅  
 [受支持的代码更改 （C# 和 Visual Basic](../debugger/supported-code-changes-csharp.md)   
 [编辑并继续 (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)