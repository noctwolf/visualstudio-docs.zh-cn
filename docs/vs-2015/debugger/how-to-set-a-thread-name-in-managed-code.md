---
title: 如何： 在托管代码中设置线程名称 |Microsoft Docs
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
helpviewer_keywords:
- Thread.Name property
- threading [Visual Studio], names
- thread names
- debugging [Visual Studio], threads
ms.assetid: c0c4d74a-0314-4b71-81c9-b0b019347ab8
caps.latest.revision: 31
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0175bee3280f3ecfdb49fc280007810d4e1c2860
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481602"
---
# <a name="how-to-set-a-thread-name-in-managed-code"></a>如何：在托管代码中设置线程名称
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 在托管代码中设置线程名称](https://docs.microsoft.com/visualstudio/debugger/how-to-set-a-thread-name-in-managed-code)。  
  
在 Visual Studio 的任何版本中都可以使用线程命名功能。 线程命名功能用于跟踪中的线程非常有用**线程**窗口。 因为**线程**窗口不可用的 Visual Studio 速成版中，线程命名功能在 Express 版本中的小实用程序。  
  
 若要在托管代码中设置线程名称，请使用 <xref:System.Threading.Thread.Name%2A> 属性。  
  
## <a name="example"></a>示例  
  
```  
Public Class Needle  
    ' This method will be called when the thread is started.  
    Sub Baz()  
        Console.WriteLine("Needle Baz is running on another thread")  
    End Sub  
End Class  
  
Sub Main()  
    Console.WriteLine("Thread Simple Sample")  
    Dim oNeedle As New Needle()  
   ' Create a Thread object.   
    Dim oThread As New System.Threading.Thread(AddressOf oNeedle.Baz)  
    ' Set the Thread name to "MainThread".  
    oThread.Name = "MainThread"  
    ' Starting the thread invokes the ThreadStart delegate  
    oThread.Start()  
End Sub  
```  
  
## <a name="see-also"></a>请参阅  
 [调试多线程应用程序](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [如何：在本机代码中设置线程名称](../debugger/how-to-set-a-thread-name-in-native-code.md)



