---
title: 如何： 出现异常后检查系统代码 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, exceptions
- exceptions, debugging
ms.assetid: a38ad49b-7cf3-483d-91c4-eb3116eba50c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a8a1da63e47514771a868b69ee798f71265fdb42
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31472460"
---
# <a name="how-to-examine-system-code-after-an-exception"></a>如何：在发生异常后检查系统代码
发生异常时，你可能需要检查系统调用内部的代码，以确定该异常的起因。 如果你没有为系统代码加载符号，或者启用了“仅我的代码”，则下面的步骤说明了如何执行此操作。  
  
### <a name="to-examine-system-code-following-an-exception"></a>在发生异常后检查系统代码  
  
1.  在**调用堆栈**窗口中，右键单击，然后单击**显示外部代码**。  
  
     如果未启用“仅我的代码”，则快捷菜单中不提供此选项，默认情况下显示系统代码。  
  
2.  右键单击现在显示在中的外部代码帧**调用堆栈**窗口。  
  
3.  指向**负载符号从**，然后单击**Microsoft 符号服务器**。  
  
    1.  如果启用了“仅我的代码”，则将显示一个对话框。 它指出“仅我的代码”现在已禁用。 要单步执行系统调用，必须这样做。  
  
    2.  **下载公共符号**对话框随即出现。 下载完毕后会自动关闭该对话框。  
  
4.  你现在可以检查系统代码中的**调用堆栈**窗口和其他窗口。 例如，你可以双击调用堆栈帧在源中查看的代码或**反汇编**窗口。  
  
## <a name="see-also"></a>请参阅  
 [管理调试器的异常](../debugger/managing-exceptions-with-the-debugger.md)