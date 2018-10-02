---
title: Microsoft Visual Studio 调试器 （引发异常） 对话框 |Microsoft Docs
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
- vs.debug.exceptions.thrown
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Microsoft Visual Studio Debugger (Exception Thrown) dialog box
- exception handling, during debugging
- debugger, exceptions
- throwing exceptions, during debugging
ms.assetid: 1fe98d10-c8f9-4b39-a920-99169bfd542e
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1d2b27620cbc37bd771fff364d06a1a33d9c8b07
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482927"
---
# <a name="microsoft-visual-studio-debugger-exception-thrown-dialog-box"></a>“Microsoft Visual Studio 调试器（引发异常）”对话框
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[Microsoft Visual Studio 调试器 （引发异常） 对话框的](https://docs.microsoft.com/visualstudio/debugger/microsoft-visual-studio-debugger-exception-thrown-dialog-box)。  
  
程序中发生了异常。 此对话框报告引发异常的类型。 您的代码需要处理此异常。 可从下列用于处理异常的选项中进行选择：  
  
 **中断**  
 允许执行中断调试器。 在中断之前不调用异常处理程序。 如果您从中断继续执行，则将调用异常处理程序。  
  
 **Continue**  
 允许执行继续，并使异常处理程序有机会处理异常。 此选项对某些类型的异常不可用。 **继续**将允许应用程序以继续。 在本机应用程序中，它将导致再次引发异常。 在托管应用程序中，它使程序终止或由主机应用程序处理异常。  
  
> [!NOTE]
>  在托管代码中出现未经处理的异常后将无法继续。 选择**继续**在托管代码中未经处理的异常导致调试停止后。  
  
 **忽略**  
 允许执行继续，但不调用异常处理程序。 由于未调用异常处理程序，这会导致更严重的后果，包括更多的异常和错误。 此选项对某些类型的异常不可用。  
  
## <a name="see-also"></a>请参阅  
 [管理调试器的异常](../debugger/managing-exceptions-with-the-debugger.md)   
 [异常的最佳做法](http://msdn.microsoft.com/library/f06da765-235b-427a-bfb6-47cd219af539)   
 [异常处理](http://msdn.microsoft.com/library/ccb11fe8-6938-41ac-b477-a183e85865b9)



