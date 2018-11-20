---
title: 启用调试 Visual c + + 中的功能 (-D_DEBUG) |Microsoft Docs
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
- vs.debug
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- /D_DEBUG compiler option [C++]
- debugging [C++], enabling debug features
- debugging [MFC], enabling debug features
- assertions, enabling debug features
- D_DEBUG compiler option
- MFC libraries, debug version
- debug builds, MFC
- _DEBUG macro
ms.assetid: 276e2254-7274-435e-ba4d-67fcef4f33bc
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf560bcde09b9d2e3c2bee689c92c9900c6e2af5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51760604"
---
# <a name="enabling-debug-features-in-visual-c-ddebug"></a>在 Visual C++ 中启用调试功能 (/D_DEBUG)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在中[!INCLUDE[vcprvc](../includes/vcprvc-md.md)]，调试功能，如当符号重新编译程序时，启用断言 **_DEBUG**定义。 您可以定义 **_DEBUG**中两种方式之一：  
  
- 指定 **#define _DEBUG**在源代码中或  
  
- 指定 **/D_DEBUG**编译器选项。 (如果在使用向导，Visual Studio 中创建你的项目 **/D_DEBUG**调试配置中自动定义。)  
  
  当 **_DEBUG**是定义，则编译器将编译包围的代码的部分 **#ifdef _DEBUG**和`#endif`。  
  
  MFC 程序的调试配置必须与 MFC 库的调试版本链接。 MFC 标头文件确定要链接的 MFC 库的正确版本根据已定义，如符号 **_DEBUG**并 **_UNICODE**。 有关详细信息，请参阅[MFC 库版本](http://msdn.microsoft.com/library/3d7a8ae1-e276-4cf8-ba63-360c2f85ad0e)。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码](../debugger/debugging-native-code.md)   
 [C++ 调试配置的项目设置](../debugger/project-settings-for-a-cpp-debug-configuration.md)



