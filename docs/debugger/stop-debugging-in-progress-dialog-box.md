---
title: 停止在进度对话框中进行调试 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.stopnow
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Stop Debugging in Progress dialog box
ms.assetid: ed7ef49d-e25f-4a4d-9396-9bc7b4143117
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3a6e13967cc18fae8d837cc71ea8a91c60f2b1bb
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44281190"
---
# <a name="stop-debugging-in-progress-dialog-box"></a>“停止正在进行的调试”对话框
当调试器尝试停止调试会话，但停止会话需要一段时间时，会出现此对话框。 停止调试会话通常很快，而此对话框并不出现。 但是，有时从正在调试的所有进程中分离需要额外的时间。 如果停止会话需要的时间超过几秒钟（或者发生分离错误），则会出现此对话框。 如果此对话框经常出现，则可能是由于内部问题，您可能需要与产品支持服务联系。  
  
 可以等待进程分离，此对话框消失，或使用**立即停止**按钮强制立即终止。  
  
 **立即停止**  
 单击此按钮可立即结束调试会话。 使用**立即停止**将终止，而不是分离正在调试的进程。 如果你正在调试系统进程，终止与这些进程**立即停止**可以有意外和不需要的效果。  
  
## <a name="see-also"></a>请参阅  
 [调试器安全](../debugger/debugger-security.md)   
 [分离程序](/previous-versions/visualstudio/visual-studio-2010/x1thkxez(v=vs.100))