---
title: 如何： 查找导致程序崩溃的 DLL |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.dll
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 469d4a3f42fc749a0a7a05f4a034bde28332dc57
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49183165"
---
# <a name="how-to-find-which-dll-your-program-crashed-in"></a>如何：查找导致程序崩溃的 DLL
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

请注意]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在“工具”菜单上选择“导入和导出设置”。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
 如果应用程序在调用系统 DLL 或别人的代码时出现崩溃，则需要找出在崩溃发生时哪个 DLL 是活动的。 如果在你自己的程序外部的 DLL 中崩溃，可以标识位置使用**模块**窗口。  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>使用“模块”窗口查找崩溃发生的位置  
  
1.  记下崩溃发生的地址。  
  
2.  上**调试**菜单中，选择**Windows**，然后单击**模块**。  
  
3.  在中**模块**窗口中，找到**地址**列。 可能需要使用滚动条来查看。  
  
4.  单击**地址**要按地址对 Dll 进行排序的列顶部的按钮。  
  
5.  细查排序的列表，找到其地址包含崩溃位置的 DLL。  
  
6.  看看**名称**并**路径**列来查看 DLL 的名称和路径。  
  
## <a name="see-also"></a>请参阅  
 [如何： 调试本机 Dll](../debugger/how-to-debug-native-dlls.md)   
 [如何：使用“模块”窗口](../debugger/how-to-use-the-modules-window.md)





