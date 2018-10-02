---
title: 无可用的源 |Microsoft Docs
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
- vs.debug.nosource
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- No Source Code Available for the Current Location dialog box
ms.assetid: ed0732bc-4b8c-490f-adb1-af06869a2a6b
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4fd7643dd7334a220d1e5c78ef12bddf07af11f8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470650"
---
# <a name="no-source-available"></a>无可用的源
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[无可用源](https://docs.microsoft.com/visualstudio/debugger/no-source-available)。  
  
你的项目不包含你尝试查看代码的源代码。 原因通常双击一个模块，在没有源代码**调用堆栈窗口**或**线程窗口**。 可以继续调试，但不能使用源窗口设置断点并在此位置执行其他操作。 如果你需要设置断点，使用**反汇编窗口**相反。  
  
 在解决方案属性页中，可以更改调试器查找源文件的目录，并通知调试器忽略选定的源文件。 请参阅[调试源通用的属性，解决方案属性页对话框](../debugger/debug-source-files-common-properties-solution-property-pages-dialog-box.md)。  
  
 **浏览并找到源代码**  
 单击此链接以打开对话框，可从中浏览并找到源代码。  
  
 **显示反汇编**  
 将启动**反汇编窗口**。  
  
 **始终显示缺少的源文件的反汇编**  
 选择此选项以显示**反汇编窗口**自动时没有源，可用。 此设置还可以更改在**选项**对话框中，**调试**类别中，**常规**页上，通过选中或清除**显示反汇编如果源不可用**。  
  
## <a name="see-also"></a>请参阅  
 [调试通用属性解决方案属性页源对话框](../debugger/debug-source-files-common-properties-solution-property-pages-dialog-box.md)   
 [指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [SOS.dll（SOS 调试扩展）](http://msdn.microsoft.com/library/9ac1b522-77ab-4cdc-852a-20fcdc9ae498)



