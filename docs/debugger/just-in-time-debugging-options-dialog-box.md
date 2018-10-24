---
title: 在实时，调试时，选项对话框 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Debugger.JIT
- vs.debug.options.JIT
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Just-In-Time debugging, setting options
- Options dialog box, debugging
ms.assetid: 7f11b2e3-3fb5-449d-b07c-6ecf1d6a487d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a6736e0646193754dbd932e5501a6473ee18c7e6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49936324"
---
# <a name="just-in-time-debugging-options-dialog-box"></a>“选项”对话框 ->“调试”->“实时”
访问**中实时**页上，转到**工具**菜单，然后单击**选项**。 在中**选项**对话框框中，展开**调试**节点，然后选择**中实时**。 使用该页，你可以为托管代码、本机代码和脚本启用实时调试。 有关详细信息，请参阅[实时调试](../debugger/just-in-time-debugging-in-visual-studio.md)。  
  
 可以为以下程序类型启用实时调试：  
  
- Managed  
  
- Native  
  
- 脚本  
  
  实时调试是一种用于调试在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 的外部启动的程序的方法。 可以在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 环境之外运行在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中创建的程序。 如果已启用实时调试，则发生崩溃时会显示一个对话框，询问您是否需要调试。  
  
## <a name="associated-warnings"></a>关联警告  
 当您访问的此页**选项**对话框中，可能会看到类似这样的警告消息：  
  
 **另一个调试器已将自己注册为实时中调试程序。若要修复，请启用在实时调试或运行 Visual Studio 修复。**  
  
 如果将另一个调试器（可能为较早版本的 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 调试器）设置为实时调试器，则会出现此消息。  
  
 可能看到的另一条消息如下：  
  
 **在实时检测到调试注册错误。若要修复，请启用在实时调试或运行 Visual Studio 修复。**  
  
 如果看到上述任一这些警告，在实时调试与[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]在解决该问题之前需要管理员权限。 如果在这些条件下尝试仅作为非管理员来启用，则会看到下面的错误消息：  
  
 **访问被拒绝。管理员启用在实时调试，或修复 Visual Studio 的安装。**  
  
## <a name="see-also"></a>请参阅  
 [调试、 选项对话框](../debugger/debugging-options-dialog-box.md)   
 [如何：指定调试器设置](../debugger/how-to-specify-debugger-settings.md)