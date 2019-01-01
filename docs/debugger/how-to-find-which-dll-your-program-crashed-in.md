---
title: 如何： 查找导致程序崩溃的 DLL |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.dll
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 40f27e0bec20e1dd037beaa5f60ea648c0ccb171
ms.sourcegitcommit: a7de99f36e9ead7ea9e9bac23c88d05ddfc38b00
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2018
ms.locfileid: "52257092"
---
# <a name="how-to-find-which-dll-your-program-crashed-in-c-c-visual-basic-f"></a>如何：查找导致程序崩溃的 DLL（C#、C++、Visual Basic、F#）
  
 如果应用程序在调用系统 DLL 或别人的代码时出现崩溃，则需要找出在崩溃发生时哪个 DLL 是活动的。 如果在你自己的程序外部的 DLL 中崩溃，可以标识位置使用**模块**窗口。  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>使用“模块”窗口查找崩溃发生的位置  
  
1.  记下崩溃发生的地址。

    如果错误消息中未显示该地址，则可能需要使用其他方法来标识 DLL。 如果怀疑是系统 DLL ，则可以在调试时从 Microsoft Symbol Server [加载符号](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)。 否则，可能需要改用堆信息[创建转储文件](../debugger/using-dump-files.md)。 有多种[工具](https://blogs.msdn.microsoft.com/andrehal/2009/12/31/what-is-a-dump-and-how-do-i-create-one/)可用于创建转储文件。
  
2.  上**调试**菜单中，选择**Windows**，然后单击**模块**。  
  
3.  在中**模块**窗口中，找到**地址**列。 可能需要使用滚动条来查看。  
  
4.  单击**地址**要按地址对 Dll 进行排序的列顶部的按钮。  
  
5.  细查排序的列表，找到其地址包含崩溃位置的 DLL。  
  
6.  看看**名称**并**路径**列来查看 DLL 的名称和路径。  
  
## <a name="see-also"></a>请参阅  
 [调试 DLL 项目](../debugger/debugging-dll-projects.md)   
 [如何：使用“模块”窗口](../debugger/how-to-use-the-modules-window.md)