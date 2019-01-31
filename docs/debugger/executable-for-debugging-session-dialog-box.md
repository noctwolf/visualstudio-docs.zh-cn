---
title: 调试会话对话框的可执行文件 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.exefordebug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- executable files, specifying when debugging
- DLLs, debugging
- debugger, Executable for Debugging Session dialog box
- Executable for Debugging Session dialog box
ms.assetid: c0ddbe32-b99f-4425-acf1-f48842804f56
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8d6bc004ac9d450e0f5ea358d16bb25ab6cabecf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018743"
---
# <a name="executable-for-debugging-session-dialog-box"></a>“调试会话的可执行文件”对话框

当您尝试调试没有指定可执行文件的 DLL 时，将出现该对话框。 Visual Studio 不能直接启动 DLL。 相反，Visual Studio 将启动指定的可执行文件。 当可执行文件调用时，可以调试该 DLL。  
  
 **可执行文件名称**  
 输入调用正在调试的 DLL 的可执行文件的路径名。  
  
 **可访问项目的 URL (仅限 ATL Server)**  
 如果正在调试 ATL Server DLL，则输入可以找到项目的 URL。  
  
 输入后，这些设置存储在项目属性页中，因此无需再输入这些后续调试会话。 如果需要更改设置，您可以打开“属性页”并更改值。 有关为调试会话指定可执行文件的详细信息，请参阅[调试 DLL](../debugger/how-to-debug-from-a-dll-project.md)。  
  
## <a name="see-also"></a>请参阅

 [在 Visual Studio 中进行调试](../debugger/index.md)  
 [初探调试器](../debugger/debugger-feature-tour.md)