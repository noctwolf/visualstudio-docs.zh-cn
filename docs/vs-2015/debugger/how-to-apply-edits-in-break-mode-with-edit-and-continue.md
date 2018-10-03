---
title: 如何： 应用编辑在中断模式下使用编辑并继续 |Microsoft Docs
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
- vs.debug.variables.failededit
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
helpviewer_keywords:
- Edit and Continue [Visual Basic], applying edits in break mode
- break mode, applying code changes
- Edit and Continue, applying edits in break mode
- editing, break mode
- coding, editing in break mode
- code, editing in break mode
ms.assetid: 1eef7498-6a1f-4fba-8146-510adc6375c9
caps.latest.revision: 33
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c9b380c4a28beb50a2048eb00aa68f81bf27449
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "47588858"
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>如何：使用“编辑并继续”在中断模式下应用编辑
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 将应用在中断模式下使用编辑并继续编辑](https://docs.microsoft.com/visualstudio/debugger/how-to-apply-edits-in-break-mode-with-edit-and-continue)。  
  
可以在中断模式下使用“编辑并继续”编辑代码，然后不必停止和重新启动执行即可继续。  
  
 在以下调试方案中，“编辑并继续”不可用：  
  
-   混合模式（本机/托管）调试。  
  
-   SQL 调试。  
  
-   调试 Dr.Watson 转储。  
  
-   在未选择 **“在未经处理的异常上展开调用堆栈”** 选项的情况下，在发生未经处理的异常之后编辑代码。  
  
-   调试嵌入式运行时应用程序。  
  
-   调试具有的应用程序**将附加到**而不是运行的应用程序**启动**从**调试**菜单。  
  
-   调试优化后的代码。  
  
-   当目标为 64 位应用程序时，调试托管代码。 如果希望使用“编辑并继续”，必须将目标平台设置为 x86 (_项目_**属性**，**编译**选项卡上，**高级编译器**设置。)。  
  
-   如果由于生成错误无法生成新版本的代码，则对旧版本的代码进行调试。  
  
### <a name="to-edit-code-in-break-mode"></a>在中断模式下编辑代码  
  
1.  执行下列操作之一进入中断模式：  
  
    -   在代码中设置断点，然后选择**开始调试**从**调试**菜单，然后等待应用程序命中断点。  
  
         - 或 -  
  
    -   开始调试，然后依次**全部中断**从**调试**菜单。  
  
         - 或 -  
  
    -   异常发生时，选择**启用编辑**上**异常助手**。  
  
2.  进行所需的并且合法的代码更改。  
  
     有关详细信息，请参阅[不支持在 Visual Basic 编辑并继续编辑](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md)。  
  
    > [!NOTE]
    >  如果尝试进行“编辑并继续”所不允许的代码更改，你的编辑将被加上紫色波浪线，并且“任务列表”中会出现一项任务。 除非撤消非法的代码更改，否则将无法继续执行代码。  
  
3.  上**调试**菜单上，单击**继续**继续执行。  
  
     在你所做的编辑已并入项目并已应用的情况下，你的代码继续执行。  
  
## <a name="see-also"></a>请参阅  
 [编辑并继续在 Visual Basic 中的不支持的编辑](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md)   
 [编辑并继续 (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)



