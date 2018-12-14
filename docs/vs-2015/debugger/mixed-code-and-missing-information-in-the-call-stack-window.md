---
title: 混合代码和调用堆栈窗口中缺少的信息 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f4ae8e527e5f6ce04680c444baad58802bfad48
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51788920"
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>“调用堆栈”窗口中的混合代码与丢失信息
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

由于托管代码和本机代码的调用堆栈之间存在差异，因此当代码类型混杂时，调试器无法始终显示完整的调用堆栈。 当本机代码调用托管的代码时，你可能会在“调用堆栈”窗口中注意到以下差异：  
  
- “调用堆栈”窗口中可能缺少托管代码正上方的本机框架。 有关详细信息，请参阅[如何：在调用堆栈窗口中缺少本机框架时跳出托管代码](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md)  
  
- 对于在调试器外部启动的混合模式应用程序，“调用堆栈”窗口可能仅显示托管代码，而不会显示任何本机框架。  
  
  这两种情况都极为少见。 在多数对托管代码的本机调用中，都会正确显示调用堆栈。  
  
## <a name="see-also"></a>请参阅  
 [如何：使用“调用堆栈”窗口](../debugger/how-to-use-the-call-stack-window.md)





