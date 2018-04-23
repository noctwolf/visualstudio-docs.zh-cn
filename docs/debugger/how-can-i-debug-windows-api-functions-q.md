---
title: 如何调试 Windows API 函数？ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.api
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], Windows API functions
- NT symbols and debugging Windows API functions
- Windows API functions, debugging
- Windows API, debugging API functions
- APIs, debugging
ms.assetid: 7c126f57-62ab-4d94-9805-632d696ba1f0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 28d9aa387861de41b7d3f782fec85d8d26c7d3ae
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="how-can-i-debug-windows-api-functions"></a>如何调试 Windows API 函数？
如果要调试加载了 NT 符号的 Windows API 函数，必须执行以下步骤。  
  
### <a name="to-set-a-breakpoint-on-a-windows-api-function-with-nt-symbols-loaded"></a>若要在加载了 NT 符号的 Windows API 函数中设置断点  
  
-   输入函数名以及函数所在 DLL 的名称。 在 32 位代码中，使用函数名的修饰形式。 若要上设置断点**MessageBeep**，例如，你必须输入以下。  
  
    ```  
    {,,USER32.DLL}_MessageBeep@4  
    ```  
  
     若要获取的修饰的名称，请参阅[查看修饰名](http://msdn.microsoft.com/en-us/f79e2717-a4db-4d12-a689-69830cce2be0)。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题](../debugger/debugging-native-code-faqs.md)   
 [调试本机代码](../debugger/debugging-native-code.md)