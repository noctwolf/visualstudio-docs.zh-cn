---
title: 无可用的源 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.nosource
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- No Source Code Available for the Current Location dialog box
ms.assetid: ed0732bc-4b8c-490f-adb1-af06869a2a6b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 671593cf19eab22d1b7e233481ee4004ca8ed8ee
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54925094"
---
# <a name="no-source-available"></a>无可用的源
你的项目不包含你尝试查看代码的源代码。 原因通常是双击了“调用堆栈”窗口或“线程”窗口中没有源代码的模块。 可以继续调试，但不能使用源窗口设置断点并在此位置执行其他操作。 如果需要设置断点，请改用“反汇编”窗口。  
  
 在解决方案属性页中，可以更改调试器查找源文件的目录，并通知调试器忽略选定的源文件。 请参阅[调试源通用的属性，解决方案属性页对话框](../debugger/debug-source-files-common-properties-solution-property-pages-dialog-box.md)。  
  
 **浏览并找到源代码**  
 单击此链接以打开对话框，可从中浏览并找到源代码。  
  
 **显示反汇编**  
 启动“反汇编窗口”。  
  
 **始终显示缺少的源文件的反汇编**  
 选择此选项可在无可用源时自动显示“反汇编窗口”。 还可通过在“选项”对话框、“调试”类别、“常规”页面中选择或清除“源代码不可用时显示反汇编”来更改此设置。  
  
## <a name="see-also"></a>请参阅  
 [“调试源文件”、“通用属性”、“解决方案属性页”对话框](../debugger/debug-source-files-common-properties-solution-property-pages-dialog-box.md)   
 [指定符号 (.pdb) 文件和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [SOS.dll（SOS 调试扩展）](/dotnet/framework/tools/sos-dll-sos-debugging-extension)