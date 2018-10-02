---
title: 混合代码和调用堆栈窗口中缺少的信息 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
helpviewer_keywords:
- managed code, stepping
- Call Stack window, mixed-mode debugging
- Call Stack window, troubleshooting
- native frames
- managed call stacks
- mixed-mode debugging, call stack
- stepping, out of managed code
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c91b2e49dc94057ab7929380ad1b819cd01731d6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478600"
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>“调用堆栈”窗口中的混合代码与丢失信息
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[混合代码与在调用堆栈窗口中缺少信息](https://docs.microsoft.com/visualstudio/debugger/mixed-code-and-missing-information-in-the-call-stack-window)。  
  
由于托管代码和本机代码的调用堆栈之间存在差异，因此对于混合的代码类型，调试器不能始终显示完整的调用堆栈。 当本机代码调用托管的代码时，可能会注意到在以下差异**调用堆栈**窗口：  
  
-   立即之上的托管代码的本机框架中可能缺少**调用堆栈**窗口。 有关详细信息，请参阅[如何： 在调用堆栈窗口中的缺少本机框架时跳出托管代码](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md)。  
  
-   对于混合模式应用程序在调试器以外启动**调用堆栈**窗口可能会显示仅托管的代码而不显示任何本机框架。  
  
 这两种情况都极为少见。 在多数对托管代码的本机调用中，都会正确显示调用堆栈。  
  
## <a name="see-also"></a>请参阅  
 [如何：使用“调用堆栈”窗口](../debugger/how-to-use-the-call-stack-window.md)





