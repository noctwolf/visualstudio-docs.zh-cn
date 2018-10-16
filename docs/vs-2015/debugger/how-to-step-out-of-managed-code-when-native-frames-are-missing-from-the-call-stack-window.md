---
title: 如何： 在调用堆栈窗口中的缺少本机框架时跳出托管代码 |Microsoft Docs
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
- Call Stack window, missing native frames
- code, managed code
- native frames
- stepping, out of managed code
- managed code, stepping out of
ms.assetid: 97cdd2a8-02a9-4a06-a5b1-c92b1e431979
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2648d73887f79f9b71770164a620bb1a8d674622
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49279430"
---
# <a name="how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window"></a>如何：在“调用堆栈”窗口中缺少本机框架时跳出托管代码
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

如果你的代码具有本机框架，则在不可见**调用堆栈**窗口中，单步执行托管代码之外可能产生意外的结果。 作为一种解决方法，您可以使用断点来代替**单步跳出**。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-display"></a>要在本机框架从调用堆栈显示中消失时跳出托管代码  
  
1.  在本机代码中，调用托管代码的后面设置一个位置断点。  
  
2.  上**调试**菜单中，选择**继续**。  
  
     托管调用完成后，执行会在本机代码的断点处停止。  
  
## <a name="see-also"></a>请参阅  
 [如何：使用“调用堆栈”窗口](../debugger/how-to-use-the-call-stack-window.md)





