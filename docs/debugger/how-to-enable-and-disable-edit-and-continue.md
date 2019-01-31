---
title: 如何：启用和禁用编辑并继续 |Microsoft Docs
ms.custom: seodec18
ms.date: 10/04/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: a201dab58084476f0993304d961fc5afa5693782
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55002224"
---
# <a name="how-to-enable-and-disable-edit-and-continue-c-vb-c"></a>如何：启用和禁用编辑并继续 (C#，VB、 c + +)

您可以禁用或启用**编辑并继续**在 Visual Studio**选项**在设计时对话框。 “编辑并继续”仅在调试版本中起作用。 有关详细信息，请参阅[编辑并继续](../debugger/edit-and-continue.md)。 
  
本机 c + +**编辑并继续**需要使用`/INCREMENTAL`选项。 有关 c + + 中的功能要求的详细信息，请参阅此[博客文章](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/)并[编辑并继续 （Visual c + +）](../debugger/edit-and-continue-visual-cpp.md)。
  
**若要启用或禁用编辑并继续：**  
  
1.  如果您在调试会话中，停止调试 (**调试** > **停止调试**或**Shift**+**F5**).

1.  在中**工具** > **选项**> (或**调试** > **选项**) >**调试** > **常规**，选择**编辑并继续**右窗格中。  
  
    > [!NOTE]
    >  如果启用了 IntelliTrace 并且收集 IntelliTrace 事件和调用信息，则会禁用“编辑并继续”。 有关详细信息，请参阅[IntelliTrace](../debugger/intellitrace.md)。
    
1.  对于 c + + 代码，请确保**启用本机编辑并继续**选择，并设置其他选项：
    - **继续应用更改（仅限本机）**  
      
      如果选中，Visual Studio 将自动编译并继续调试从中断状态时应用代码更改。 否则，你可以选择将应用使用的更改**调试** > **应用代码更改**。  
      
    - **警告过时代码（仅限本机）**  
      
      如果选择，提供了关于陈旧代码警告。 
  
1.  单击 **“确定”**。    
